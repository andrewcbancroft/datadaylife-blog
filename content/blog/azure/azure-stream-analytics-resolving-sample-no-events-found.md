---
title: "Resolving No Events Found When Sampling Data with Azure Stream Analytics"
author: "Andrew Bancroft"
date:   2019-01-04
description: "No events found for HubName... Ugh. If you are pretty sure data is making it to the Hub, but you are unable to get Stream Analytics to sample from the stream, check out how I was able to resolve this issue."
type: blog
draft: false
comments: true
aliases:
    - /azure-stream-analytics-resolving-sample-no-events-found/
---

Data is making it to the Event Hub...at least you're 99% sure it is, because successful requests are being made by your app/device and received by the Hub.

The trouble is, when you attempt to sample data with Azure Stream Analytics, you come up empty with a message like

> No events found for `HubName`.

or

> Diagnostics: While sampling data, no data was received from `#` partitions.

In my particular case, everything was fine with both the Event Hub and the Stream Analytics Job configurations. My issue was **how my client app was encoding things as JSON**.

I was using Node to simulate a device sending data to the Event Hub.

I had a standard import of the required library objects, and the creation of an `EventHubClient` as follows:

```js
const { EventHubClient, EventPosition } = require('@azure/event-hubs');
const client = EventHubClient.createFromConnectionString(process.env["EVENTHUB_CONNECTION_STRING"], process.env["EVENTHUB_NAME"]);
```

But my `main` function contained a flaw. It was sending valid JSON, but not in the "shape" that Azure Stream Analytics expected it.  It resulted in a JSON parsing error.

What was the flaw?  Compare the following snippets inline:

```js
function main() {
    const incorrectDataFormat = { DeviceID: "SomeDeviceID", LocationID: "SomeLocationID", Measurement: "SomeMeasurement" };
    const CORRECTDataFormat = { body: { DeviceID: "SomeDeviceID", LocationID: "SomeLocationID", Measurement: "SomeMeasurement" } };
    
    client.send(incorrectDataFormat); // won't get picked up by Stream Analytics
    client.send(CORRECTDataFormat); // WILL get picked up by Stream Analytics
}
```

What's the difference?

For receiving events from Azure Stream Analytics, you've got to send Events to an EventHub where the **body** is a JSON object/array...which means you've got to have a `body` property with a *value*...an object, or an array... that contains the data you want to send.

`const CORRECTDataFormat = { body: { DeviceID: "SomeDeviceID", LocationID: "SomeLocationID", Measurement: "SomeMeasurement" } };`

If you're running into issues with sampling Event Hub data using Stream Analytics, it might be worth the effort to double-check that the structure of your JSON object is in line with the expectation described above. 🙌🏻

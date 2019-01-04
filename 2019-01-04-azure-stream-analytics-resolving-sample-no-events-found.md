---
title: Resolving "No Events Found" When Sampling Data with Azure Stream Analytics
excerpt: ""
layout: draft
toc: true
categories: [Data Modeling]
---

No events found for `HubName`.

Diagnostics: While sampling data, no data was received from `#` partitions.

const { EventHubClient, EventPosition } = require('@azure/event-hubs');

const client = EventHubClient.createFromConnectionString(process.env["EVENTHUB_CONNECTION_STRING"], process.env["EVENTHUB_NAME"]);

async function main() {
    // NOTE: For receiving events from Azure Stream Analytics, please send Events to an EventHub where the body is a JSON object/array.
    // const eventData = { body: { "message": "Hello World" } };
    const data = { body: "Hello World 1" };
    const delivery = await client.send(data);
    console.log("message sent successfully.");
}

main().catch((err) => {
    console.log(err);
});

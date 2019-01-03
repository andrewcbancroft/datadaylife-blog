---
title: Deciphering U-SQL's Error Messages
excerpt: "When your U-SQL Job fails, look closely at the Details secion of the message to decipher what's going on."
layout: single
toc: true
categories: [Big Data, Azure Data Lake Analytics, U-SQL]
---

It's inevitable - you're going to encounter job failures when working with Azure Data Lake Analytics U-SQL jobs.

# Error Sources
There are at least three root causes for a U-SQL job failure:

1) A problem with your **script**

2) A problem with the **data**

3) A problem with your extractor's "**shematizing**" of your data

# Deciphering Error Messages
Whenever an error is reported, it can be helpful to slow down and read through the feedback that the Azure Data Lake Analytics service gave you.

Here's my general approach to deciphering error messages produced by the Azure Data Lake Analytics service:

1) Read the "Message" portion of the error to get a general feel for what the service didn't like.

2) Decide where the root cause was:  The script?  The data?  The extrator's schematizing of your data?

3) Read the "Detail" section and **look for the position of the `###` symbols**

This is your biggest clue about where the job service encountered a problem that it didn't know how to recover from.

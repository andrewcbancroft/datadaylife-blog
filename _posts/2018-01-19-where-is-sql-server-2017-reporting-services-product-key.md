---
title: Where is the SQL Server 2017 Reporting Services License Key??
excerpt: "After running the SQL Server 2017 Reporting Services standalone installer, you'll be presented with a dialog asking for a Product Key.  Where is it??"
layout: single
toc: true
date: 2018-01-19
categories: [SQL Server]
---
SQL Server 2017 Reporting Services is no longer bundled with the main SQL Server installer, so if you're looking to add the Reporting Services 2017 feature, you need to run the [stand-alone installer](https://www.microsoft.com/en-us/download/details.aspx?id=55252).

When you run said installer, you'll be presented with a dialog asking for a product key.

![Prompt for product key]({{ "/assets/ssrs2017-product-key.png" | relative_url }})

But uhhhh... Where is it?

Naturally, we went to our Volume Licensing Portal, but Reporting Services 2017 isn't listed.  

Additionally, we looked for a SQL Server 2017 key, but the portal indicated that our copy of SQL Server "didn't require" a product key.

Why?  Because it's *embedded* into the SQL Server 2017 installer itself.

Bingo.

## Re-run the SQL Server 2017 Installer
If you re-run the SQL Server 2017 installer, and just Next Next Next to the **Product Key** screen, you can copy and paste the key from there.

![Prompt for product key]({{ "/assets/sql-server-2017-product-key.png" | relative_url }})

Simple.  Hopefully this saves you 30 minutes running around to different portals trying to find a key that's "hidden" right in front of you. 👐

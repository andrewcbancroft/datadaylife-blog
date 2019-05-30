---
title: "U-SQL Pickiness - Resolving Common Syntax Errors"
author: "Andrew Bancroft"
date:   2019-01-02
description: "Here are a few gotchas to look out for newcommers writing U-SQL for Azure Data Lake Analytics from a T-SQL background."
type: blog
draft: false
comments: true
aliases:
    - /u-sql-pickiness-resolving-common-syntax-errors/
---

Newbies to U-SQL from T-SQL will soon run face-first into the wall that I ran into.

Where T-SQL isn't picky about stuff like **capitalization** and **terminating semicolons**, U-SQL definitely is.

If you happen to fail at capitalizing one of the U-SQL keywords like `SELECT` or `FROM`, or if you miss a `;` somewhere, you'll get a syntax error:

> syntax error. Expected one of: '.' ALL ANTISEMIJOIN ANY AS BEGIN BROADCASTLEFT BROADCASTRIGHT CROSS DISTINCT EXCEPT FULL FULLCROSS GROUP HASH HAVING INDEXLOOKUP INNER INTERSECT JOIN LEFT LOOP MERGE ON OPTION ORDER OUTER OUTER UNION PAIR PIVOT PRESORT PRODUCE READONLY REQUIRED RIGHT SAMPLE SEMIJOIN SERIAL TO UNIFORM UNION UNIVERSE UNPIVOT USING WHERE WITH ';' '(' ')' ','

If you fail to capitalize `AS`, you'll get this fun one:

> SELECT expression is missing an AS alias, did you mean to capitalize [as]?

**Takeaway:**  Make sure your "more casual" writing of T-SQL doesn't carry over to U-SQL.  If you're getting interesting syntax errors, double-check your script to ensure you've got correct capitalization and semicolons after each statement.

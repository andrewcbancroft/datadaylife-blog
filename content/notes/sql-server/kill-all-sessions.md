---
title: "Kill All Sessions"
author: "Andrew Bancroft"
date:   2018-01-09
description: "Script to close all sessions/connections to a specified database"
type: technical_note
draft: false
comments: true
aliases:
    - /sqlserverscripts/kill-all-sessions/
---

```sql
USE master;
GO

ALTER DATABASE [DatabaseName]
SET SINGLE_USER
WITH ROLLBACK IMMEDIATE;
ALTER DATABASE [DatabaseName]
SET MULTI_USER;
GO
```

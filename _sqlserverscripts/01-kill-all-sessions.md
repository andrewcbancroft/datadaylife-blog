---
title: "Kill all Sessions"
excerpt: "Script to close all sessions/connections to a specified database"
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

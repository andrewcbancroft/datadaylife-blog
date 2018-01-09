---
title: "Get Out of SINGLE_USER Mode"
permalink: /sqlserverscripts/get-out-of-single-user-mode/
exerpt: "Process for getting a SQL Server database out of SINGLE_USER Mode if you're stuck in it."
last_modified_at: "2018-01-09"
date: "2018-01-09"
---

If you find yourself stuck in `SINGLE_USER` mode in a SQL Server database, do the following:

## 1 - Find SPIDs connected to your database
```sql
USE master
GO
EXEC sp_who
```

Note any SPIDs connected to your database, and then...

## 2 - Kill connections
```sql
KILL [spid] -- do this for each spid returned by exec sp_who
```

## 3 - Set back to MULTI_USER
```sql
USE Master
ALTER DATABASE DatabaseName SET MULTI_USER
```

## Plan B (If that doesn't work)
If that doesn't work, the following query can be used to find the connection(s):

```sql
SELECT
	request_session_id
FROM
	sys.dm_tran_locks
WHERE
	resource_database_id = DB_ID('DatabaseName')
```

Note any spid's that are returned, and then run

```sql
KILL [spid] -- do this for each spid returned by the previous query


USE Master
ALTER DATABASE YourDatabase SET MULTI_USER
```

Source:  [Stack Overflow](https://stackoverflow.com/questions/24608702/sql-server-2008-r2-stuck-in-single-user-mode)

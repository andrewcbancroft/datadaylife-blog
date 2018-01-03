---
title: "Search Database Objects for Text"
permalink: /sqlserverscripts/search-objects-for-text/
exerpt: "If you need to find some text within a database object like a stored procedure, function, view, trigger, etc. this script can be helpful."
---

If you need to find some text within a database object, this script can be helpful.

It should allow you to find text within the following types of database objects:
* Functions (scalar and table-valued)
* Stored Procedure
* Trigger
* View

```sql
DECLARE @SearchString VARCHAR(255)
SET @SearchString = 'TextToFind'

SELECT DISTINCT
	o.name AS ObjectName,
	o.type_desc as TypeDescription
FROM
	sys.sql_modules m
	INNER JOIN sys.objects o ON m.object_id = o.object_id
WHERE
	m.[definition] LIKE '%' + @SearchString + '%'
ORDER BY
	2, 1
```

An alternative script that I've used for a long time is as follows:
```sql
DECLARE @SearchString VARCHAR(255)
SET @SearchString = 'TextToFind'

SELECT
	OBJECT_NAME(id),
	*
FROM
	SYSCOMMENTS
WHERE
	[text] LIKE '%' + @SearchString + '%'
```
Source: [Stack Overflow](https://stackoverflow.com/questions/674623/how-to-find-a-text-inside-sql-server-procedures-triggers)
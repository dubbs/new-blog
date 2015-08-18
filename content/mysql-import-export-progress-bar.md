Title: MySQL Import/Export Progress Bar
Date: 2013-09-05 22:05
Modified: 2013-09-05 22:05
Category: Programming
Tags: unix, sql

MySQL command line progress can be monitored using the terminal-based "Pipe Viewer" `pv`.

## Import

```bash
pv /path/to/sqlfile.sql | mysql -uUSERNAME -pPASSWORD -D DATABASE_NAME
```

## Export

We need to estimate the file size of our export to get an accurate reading.  This can be done via the information schema:

```sql
SELECT
  Data_BB / POWER(1024,1) Data_KB,
  Data_BB / POWER(1024,2) Data_MB,
  Data_BB / POWER(1024,3) Data_GB
FROM (
  SELECT SUM(data_length) Data_BB
  FROM information_schema.tables
  WHERE table_schema IN ('DATABASE_NAME')
) A;
```

We then use the estimated size to track export progress: 

```bash
mysqldump -uUSERNAME -pPASSWORD DATABASE_NAME | pv -s 9999M > DATABASE_NAME.sql
```

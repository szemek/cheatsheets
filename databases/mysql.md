### Show databases

```sql
SHOW DATABASES;
```

### Use specific database

```sql
USE database_name;
```

### Show information about columns from table

```sql
SHOW FIELDS from table_name;
```

### Show indexes from table

```sql
SHOW INDEXES FROM table_name;
```

### Insert row

```sql
INSERT INTO table_name (column_name_1, ...) VALUES (value_1, ...);
```

### List users

```sql
SELECT user, host FROM mysql.user;
```

### Show privileges

```sql
SHOW GRANTS FOR 'user'@'localhost';
```

### Grant privileges

```sql
GRANT ALL PRIVILEGES ON *.* TO 'user'@'%';
```

### Adding user accounts

http://dev.mysql.com/doc/refman/5.7/en/adding-users.html

### Get info about tables

```sql
SELECT * FROM information_schema.TABLES;
```

### Reset root password

http://dev.mysql.com/doc/refman/5.7/en/resetting-permissions.html#resetting-permissions-unix


### Temporarily disable foreign key checks or constraints

```sql
SET foreign_key_checks = 0;
-- ... query ...
SET foreign_key_checks = 1;
```

### Show number of currently open connections

```sql
SHOW STATUS WHERE `Variable_name` = 'Threads_connected';
```

### Show process list

```sql
SHOW PROCESSLIST;

SELECT * FROM information_schema.processlist;
```

### Show `max_connections` variable

```sql
SHOW VARIABLES LIKE "max_connections";
```

### Set `max_connections` variable

```sql
SET GLOBAL max_connections = 10000;
```

### Show statistics about tables, e.g number of rows, data length

```
SELECT TABLE_SCHEMA, TABLE_NAME, TABLE_ROWS, DATA_LENGTH
FROM information_schema.PARTITIONS
ORDER BY data_length DESC;
```

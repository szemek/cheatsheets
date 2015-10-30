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

### Get info about tables

```sql
SELECT * FROM information_schema.TABLES;
```

### Reset root password

http://dev.mysql.com/doc/refman/5.7/en/resetting-permissions.html#resetting-permissions-unix


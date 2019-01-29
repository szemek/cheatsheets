## Redshift

### Connect to Redshift

```
psql -h host -U username -d database -p 5439
```

### List databases

```
\l
```

### List tables

```
SELECT * FROM pg_tables;
```

### List users

```
SELECT * FROM pg_user;
```

### Display permissions

```sql
SELECT
    u.usename,
    s.schemaname,
    has_schema_privilege(u.usename,s.schemaname,'create') AS user_has_select_permission,
    has_schema_privilege(u.usename,s.schemaname,'usage') AS user_has_usage_permission
FROM
    pg_user u
CROSS JOIN
    (SELECT DISTINCT schemaname FROM pg_tables) s
WHERE
    u.usename = 'username';
```

### Set user password

```sql
ALTER USER username WITH PASSWORD 'password';
```

### Revoke all privileges

```sql
REVOKE ALL PRIVILEGES ON ALL TABLES IN SCHEMA pg_catalog FROM username;
REVOKE ALL PRIVILEGES ON ALL TABLES IN SCHEMA information_schema FROM username;
REVOKE ALL PRIVILEGES ON ALL TABLES IN SCHEMA public FROM username;
```

### Drop user

```sql
DROP USER username;
```

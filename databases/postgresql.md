## PostgreSQL interactive terminal

```
psql
```

## PSQL

### List databases

```
\l
```

### List tables

```
\dt
```

### Create user

```sql
CREATE USER username;
```

### Change user permissions (alter role)

```sql
ALTER ROLE username SUPERUSER CREATEDB CREATEROLE REPLICATION;
```

### Set user password

```sql
ALTER USER username WITH PASSWORD 'password';
```

### Change postgres default template0 to UTF8 encoding

([gist](https://gist.github.com/ffmike/877447))

```sql
update pg_database set datallowconn = TRUE where datname = 'template0';
\c template0
update pg_database set datistemplate = FALSE where datname = 'template1';
drop database template1;
create database template1 with template = template0 encoding = 'UTF8';
update pg_database set datistemplate = TRUE where datname = 'template1';
\c template1
update pg_database set datallowconn = FALSE where datname = 'template0';
```

### Revoke connect access to database

```sql
REVOKE connect ON DATABASE database_name FROM PUBLIC;
```

### Grant connect access on database to user/role

```sql
GRANT connect ON DATABASE database_name TO rolename;
```

### Show `statement_timeout`

```sql
SELECT setting
FROM pg_settings
WHERE name = 'statement_timeout';
```

### Terminate existing connections

https://stackoverflow.com/a/5408501

```sql
SELECT pg_terminate_backend(pg_stat_activity.pid)
FROM pg_stat_activity
WHERE pg_stat_activity.datname = 'TARGET_DB' -- ← change this to your DB
  AND pid <> pg_backend_pid();
```

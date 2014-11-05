### PostgreSQL interactive terminal

```
psql
```

### List of databases

```
\l
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

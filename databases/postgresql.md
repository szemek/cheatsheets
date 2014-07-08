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

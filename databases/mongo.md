## Reference

[mongo Shell Quick Reference](https://docs.mongodb.org/manual/reference/mongo-shell/)

### Print a list of all databases on the server

```
show dbs
```

### Switch current database to `<db>`

```
use <db>
```

### Copy database

```
db.copyDatabase(fromdb, todb, host[:port], fromdb_username, fromdb_password)
```

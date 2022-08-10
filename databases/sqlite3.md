## SQLite3

### Enable headers

```
.headers ON
```

### Show names of tables

```
.tables
```

```sql
SELECT name FROM sqlite_master WHERE type = 'table';
```

### Show schema

```
.schema table_name
```

```sql
SELECT sql FROM sqlite_master WHERE type = 'table' AND name = 'table_name';
```
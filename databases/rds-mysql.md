### Set binlog retention hours

```sql
CALL mysql.rds_set_configuration('binlog retention hours', 24);
```

### Show RDS configuration

```sql
CALL mysql.rds_show_configuration;
```

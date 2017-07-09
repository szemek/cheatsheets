## [Management Command Line Tool](https://www.rabbitmq.com/management-cli.html)

```
rabbitmqadmin  --username username --password password --host xx.xx.xx.xx
```

### List connections

```
rabbitmqadmin -f tsv -q list connections name
```

### Close connection


```
rabbitmqadmin -q close connection name="xx.xx.xx.xx:xxxx -> yy.yy.yy.yyy:yyyy"
```

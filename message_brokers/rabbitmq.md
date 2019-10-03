## [Management Command Line Tool](https://www.rabbitmq.com/management-cli.html)

```
rabbitmqadmin  --username username --password password --host xx.xx.xx.xx
```

### List connections

```
rabbitmqadmin -f tsv -q list connections name
```

### Close connection

#### rabbitmqadmin
```
rabbitmqadmin -q close connection name="xx.xx.xx.xx:xxxx -> yy.yy.yy.yyy:yyyy"
```

#### rabbitmqctl

```
rabbitmqctl close_connection <connectionpid> <explanation>
```

```
rabbitmqctl close_connection "<rabbit@ip-12-3-4-5.6.7890.1234>" "Disconnect"
```

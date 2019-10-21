## [Management Command Line Tool](https://www.rabbitmq.com/management-cli.html)

```
rabbitmqadmin  --username username --password password --host xx.xx.xx.xx
```

### List connections

#### rabbitmqadmin

```
rabbitmqadmin -f tsv -q list connections name
```

#### rabbitmqctl

```
rabbitmqctl list_connections pid name port host
```

rabbitmqctl(8) [list_connections](https://www.rabbitmq.com/rabbitmqctl.8.html#list_connections)

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

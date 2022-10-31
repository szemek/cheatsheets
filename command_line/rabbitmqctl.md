## rabbitmqctl

#### Add user

```
rabbitmqctl add_user username password
```

#### Set user tags

```
rabbitmqctl set_user_tags username administrator
```

#### Change password

```
rabbitmqctl change_password guest guest123
```

#### Add vhost

```
rabbitmqctl add_vhost custom-vhost
```

#### Set permissions

```
rabbitmqctl set_permissions -p custom-vhost username ".*" ".*" ".*"
```

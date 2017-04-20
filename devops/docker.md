## Docker

### Remove all containers

```
docker rm -f $(docker ps -aq)
```

### Set environment variables

```
eval $(docker-machine env default)
```

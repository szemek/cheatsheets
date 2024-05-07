## Docker


### Inspect network

```
docker network inspect bridge
```

### Display containers' IP addresses

```
docker network inspect bridge -f '{{range .Containers}}{{.IPv4Address}} {{.Name}}
{{end}}'
```

### Remove all containers

```
docker rm -f $(docker ps -aq)
```

### Set environment variables

```
eval $(docker-machine env default)
```

### Copy files from Docker container to host

```
docker create --name dummy IMAGE_NAME
docker cp dummy:/path/to/file /dest/to/file
docker rm -f dummy
```

Reference: https://stackoverflow.com/a/22050116

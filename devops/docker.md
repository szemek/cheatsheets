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

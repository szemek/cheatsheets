## nc

#### Send HTTP request to UNIX socket

```
echo -e "GET /images/json HTTP/1.0\r\n" | nc -U /var/run/docker.sock
```

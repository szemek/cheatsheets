## socat

https://medium.com/@copyconstruct/socat-29453e9fc8a6


#### Forward local port to remote one

```
socat tcp-listen:6379,reuseaddr,fork tcp:remote.example.com:6379
```

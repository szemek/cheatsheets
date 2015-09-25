[Redis commands](http://redis.io/commands)

### Monitor changes

```
MONITOR
```

### Clear keys with `prefix`

```
EVAL "return redis.call('del', unpack(redis.call('keys', ARGV[1])))" 0 prefix:*
```

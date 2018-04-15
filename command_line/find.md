## find

#### Remove all files except one

```
find . ! -name 'file.txt' -type f -exec rm -f {} +
```

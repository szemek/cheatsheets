# Shell

## Dynamic aliases

```
function dynamic_aliases {
  local PROJECT="/path/to/project/directory"
  for directory in $( ls $PROJECT ); do
    if [ -d "$PROJECT/$directory" ]; then
      alias $directory="cd $PROJECT/$directory"
    fi
  done
}

dynamic_aliases
```

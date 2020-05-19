### Database connection details

```ruby
ActiveRecord::Base.connection_config
```

```ruby
SomeModel.connection_config
```

### Run raw SQL from ActiveRecord

```ruby
ActiveRecord::Base.connection.execute('... sql query ...').to_a
```

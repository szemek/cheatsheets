## InfluxDB

### Command-line

`influx`

#### Show databases

```
SHOW DATABASE
```

#### Create user

https://docs.influxdata.com/influxdb/latest/administration/authentication_and_authorization

```
CREATE USER admin WITH PASSWORD '<password>' WITH ALL PRIVILEGES
```

#### Create new database

```
CREATE DATABASE <database>
```

#### Select database for use

```
USE <database>
```

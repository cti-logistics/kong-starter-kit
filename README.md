Clone the project

```
$ git clone https://github.com/cti-logistics/kong-starter-kit.git
$ cd kong-starter-kit
```

Create new .env file within folder

```
TOKEN_SECRET=TOKEN_SECRET_STRING
```

Deploy kong, cassandra, konga stack

```
$ docker-compose up -d
```

Prepare database for kong

```
$ docker  run --rm \
--network simple-kong_default \
-e "KONG_DATABASE=cassandra" \
-e "KONG_CASSANDRA_CONTACT_POINTS=kong-database" \
kong:2.4-alpine kong migrations bootstrap
```

Manage kong

```
http://<server-ip>:1337
```

### Postgres as a datasource

Install datucore with extras postgres

```
pip install "datu-core[postgres]"
```

In profiles.yml

```
dev-postgres:
    type: postgres
    host: [hostname]
    user: [username]
    password: [password]
    port: [port]
    dbname: [database name]
    schema: [schema]
```

### Postgres as a datasource

Install datucore with extras postgres

```sh
pip install "datu-core[postgres]"
```

In profiles.yml

```sh
dev-postgres:
    type: postgres
    host: [hostname]
    user: [username]
    password: [password]
    port: [port]
    dbname: [database name]
    schema: [schema]
```
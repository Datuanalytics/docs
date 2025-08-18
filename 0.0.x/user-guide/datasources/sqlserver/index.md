### Sqlserver as a datasource

Install datucore with extras postgres

```
pip install "datu-core[sqldb]"
```

For sqlserver to work you have to make sure the below ODBC driver is installed on your machine according to the Operating System.

[Install ODBC driver](https://learn.microsoft.com/en-us/sql/connect/python/pyodbc/step-1-configure-development-environment-for-pyodbc-python-development?view=sql-server-ver16&tabs=windows)

In profiles.yml

```
dev-sqlserver:
    type: sqlserver
    driver: 'ODBC Driver 18 for SQL Server' # Mandatory for sqlserver.
    host: [hostname]
    user: [username]
    password: [password]
    port: [port]
    dbname: [database name]
    schema: [schema]
```

# Datasources Overview

The directory provides a collection of configurations to help you get started with connecting data sources with Datu.
## Purpose

With Datu, you can quickly connect to your data sources and turn raw information into actionable insights.

### How to add datasources

As per the current design the application will fetch all the schema that is listed in the profiles.yml. It is to avoid fetching the schema every single time.But it will only work on the **target** datasource that is selected.

**Structure of profiles.yml**

```sh
datu_demo:
  target: dev-postgres # Target is used to select the datasource that is currently active. Change this if you would like to use a different datasource.
  outputs:
    dev-postgres:
      type: postgres
      {% raw %}
      host: "{{ env_var('DB_HOST', 'localhost') }}"  # if a environment variable is supplied that gets priority. This is useful for not hardcoding.
      {% endraw %}
      port: 5432
      user: postgres
      password: postgres
      dbname: my_sap_bronze
      schema: bronze
    dev-sqlserver:
      type: sqlserver
      driver: 'ODBC Driver 18 for SQL Server' # Mandatory for sqlserver.
      host: localhost
      port: 1433
      user: sa
      password: Password123!
      dbname: my_sap_bronze
      schema: bronze
```

### About profiles.yml

Datu core needs profiles.yml file that contains all the datasources configured. If you have used [dbt](https://github.com/dbt-labs/dbt-core),this is somewhat like to their profiles.yml though not exaclty the same.

```sh
<profile-name>:
  target: <target-name> # this is the default target
  outputs:
    <target-name>:
      type: <postgres | sqlserver | other>
      schema: <schema_identifier>

      ### Look for each datasources specific variables
      ...

      ...

<profile-name>: # additional profiles
  ...

```

### env_var

You can use `env_var` with any attribute in the `profiles.yml` `outputs` section to load configuration values from environment variables.  

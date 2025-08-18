# Datu AI Analyst

This quickstart guide shows you how to spin up your Datu server, add datasources and integrate mcp servers to your agent and emit debug logs.
After completing this guide you can deploy to production and running at scale.

## Install Datu from PyPI.

First, ensure that you have Python 3.11+ installed.

We'll create a virtual environment to install the Datu and its dependencies in to.

```bash
python -m venv .venv
```

And activate the virtual environment:

* macOS / Linux: `source .venv/bin/activate`
* Windows (CMD): `.venv\Scripts\activate.bat`
* Windows (PowerShell): `.venv\Scripts\Activate.ps1`

Next we'll install the `datu-core` server package:

```bash
pip install "datu-core[postgres]"
```

### How to add datasources

As per the current design, the application will fetch all the schema that is listed in the profiles.yml. Place profile.yml in the current directory or home directory for the application to fetch or set DATU_DBT_PROFILES="path/profiles.yml".
**Structure of profiles.yml**

```sh
my_sources:
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

## How to run datu?

After creating the datasources profiles.yml.

### 🔧 Environment Variables  

set the following environment variables:  

- **`DATU_OPENAI_API_KEY`** – your OpenAI API key  
- **`DATU_DBT_PROFILES`** – path to your `profiles.yml` 

Then run

```bash
datu
```

## Debug logs

To enable debug logs in Datu server .

**Environment variables**: Set `DATU_LOGGING_LEVEL="DEBUG"`

## Next Steps

Ready to learn more? Check out these resources:

- [Datasources](datasources/datasources.md) - Connecting multiple datasources.
- [More configurations](configurations.md) - Datu server configurations includes port, schema configurations etc.
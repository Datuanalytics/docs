# Datu AI Analyst

Install Datu

```sh
pip install "git+https://github.com/Datuanalytics/datu-analytics.git@0.0.1#egg=datu[postgres,sqldb]"
python -m spacy download en_core_web_lg # for anonymizer to work


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

### Configurations to set

All the configurations that can be used listed below with their description, default values and possible values. set them using environment variables.

#### Application run configurations

##### Host

Host where your application will be running.

```sh
DATU_HOST=0.0.0.0
```

##### Port

Port where your application listens to.

```sh
DATU_PORT=8000
```

##### Openai key

OpenAI llm key.

```sh
DATU_OPENAI_API_KEY=
```

#### Schema configurations

##### Schema refresh threshold days

Refresh schema in x days.

```sh
DATU_SCHEMA_REFRESH_THRESHOLD_DAYS=2
```

###### Schema cache file

Store schema cache to.

```sh
DATU_SCHEMA_CACHEC_FILE=schema_cache.json
```

###### Schema categorical detection

Detect categorical columns.

```sh
DATU_SCHEMA_CATEGORICAL_DETECTION=true
```

###### Schema sample limit

Schema sample limit to determine categorical values.

```sh
DATU_SAMPLE_LIMIT=1000
```

###### Schema categorical threshold

Threshold for column values to be considered as categorical.

```sh
DATU_SCHEMA_CATEGORICAL_THRESHOLD=10
```

###### SchemaRAG Engine

Extract relevant part of schema based on user query. Set to True to activate.

```sh
DATU_ENABLE_SCHEMA_RAG=False
```

#### Datasource related configuration

##### DBT profiles

Datasource profiles.yml.

```sh
DATU_DBT_PROFILES=
```



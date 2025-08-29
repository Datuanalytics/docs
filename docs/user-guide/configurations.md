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

#### MCP related configuration

##### Enable MCP Connectivity

Set the following environment variable to enable MCP connectivity in Datu:

```sh
DATU_ENABLE_MCP=true
```

##### MCP Servers Configuration
Define your MCP servers in a JSON config file (e.g. mcp_config.json):

```json
{
  "mcpServers": {
    "sql_generator": {
      "command": "python",
      "args": ["-m", "datu.mcp.tools.sql_generator"],
      "env": { "PYTHONPATH": "." }
    }
  }
}
```

#### Telemetry related configuration

##### Product telemetry

Product telemetry is enabled by default and you can disable it by

```sh
DATU_ENABLE_ANONYMIZED_TELEMETRY=false
```
# MCP Connectivity Overview

The directory provides a collection of configurations to help you get started with connecting MCP servers with Datu.

## Purpose

With Datu, you can quickly connect to your MCP servers and use your tools with the Datu AI Analyst.

# Enabling MCP Servers

To enable the MCP Connectivity in Datu, in app_config.py set 

```sh
    enable_mcp: bool = True
```

### How to MCP Servers

**Structure of MCP.yml**

```sh
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

### env_var

You can use `env_var` with any attribute in the `profiles.yml` `outputs` section to load configuration values from environment variables.  

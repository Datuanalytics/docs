# MCP Connectivity Overview

This directory provides examples and configuration files to help you connect MCP servers with Datu.\
Datu uses the [mcp-use](https://github.com/mcp-use/mcp-use) package to implement MCP clients and manage connectivity.

## Purpose

With Datu, you can connect to your MCP servers and use their tools through the Datu AI Analyst.

## Enabling MCP Servers

To enable MCP connectivity, set the following environment variable (see also [configurations.md](../../configurations/)):

```
export DATU_ENABLE_MCP=true
```

Alternatively, add it to your .env file:

```
DATU_ENABLE_MCP=true
```

### Connecting MCP Servers

MCP servers are defined in a JSON configuration file (e.g. mcp_config.json). Each server entry specifies the command, arguments, and environment needed to start it.

**Structure of mcp_config.json**

```
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

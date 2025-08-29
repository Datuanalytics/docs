# Telemetry in Datu Server

Datu Server comes with a built-in **telemetry system** that gathers **anonymous usage information**.  
This data helps the maintainers understand how the software is being used and guides ongoing improvements.

---

## Why Telemetry?

Telemetry provides valuable feedback without exposing personal or sensitive information.  
It allows the team to:

- Measure how features are being adopted.
- Detect common usage patterns and performance bottlenecks.
- Prioritize enhancements that have the greatest impact.
- Ensure the system evolves in line with real-world needs.

---

## What Data Is Collected?

The telemetry system only collects **non-identifiable, aggregated data** such as:

- Basic environment details (e.g., version, operating system).
- Which features or APIs are being exercised.
- MCP server names.
- General performance metrics.

No private data, user content, or identifiers are captured such as: usernames, hostnames, file names, environment variables, or hostnames of systems being tested.

---

## Where is telemetry information stored?

We use [Posthog](https://posthog.com/) to store and visualize telemetry data.

<div style="border: 1px solid #ccc; padding: 12px; border-radius: 6px; background-color: #f9f9f9;">
  <strong>PostHog</strong> is an open source platform for product analytics.  
  Learn more at <a href="https://posthog.com">posthog.com</a> or <a href="https://github.com/posthog">github.com/posthog</a>.
</div>

## Turning Telemetry Off

If you prefer not to share anonymous usage data, you can disable telemetry with an environment variable:

```sh
export DATU_ENABLE_ANONYMIZED_TELEMETRY=false
```

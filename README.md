# Rosie MCP Plugin

This repository contains a Codex plugin that installs the hosted Rosie MCP server and bundles skills for navigating Rosie resource discovery workflows.

## What it installs

- A remote MCP server pointing at `https://www.rosie.fyi/mcp`
- Skill guidance for category-first exploration, focused service lookup, and Rosie search telemetry review

## Included skills

- `rosie-resource-navigation`
  Uses `list_service_categories` before broad exploration and `search_resources` for targeted service lookup.
- `rosie-search-ops`
  Uses `get_search_telemetry` for search-quality, routing, and demand analysis.

## MCP server

The bundled MCP config lives in [`.mcp.json`](./.mcp.json) and points to the canonical Rosie MCP server:

```json
{
  "mcpServers": {
    "rosie": {
      "url": "https://www.rosie.fyi/mcp"
    }
  }
}
```

Rosie homepage: `https://www.rosie.fyi/`

The hosted server uses OAuth and will redirect through the Rosie sign-in flow when the client connects.

## Repository layout

- `.codex-plugin/plugin.json`
- `.mcp.json`
- `skills/`
- `assets/`

## Status

The repository is intended to be installed as a private plugin first, then opened up once the install flow is validated.

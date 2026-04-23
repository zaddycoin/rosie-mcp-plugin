# Rosie MCP Plugin

This repository contains a Codex plugin that installs the hosted Rosie MCP server and bundles skills for navigating Rosie resource discovery workflows.

It now also exposes a Claude Code marketplace manifest at [`.claude-plugin/marketplace.json`](./.claude-plugin/marketplace.json), so you can add this repository directly as a marketplace in Claude.

## Claude marketplace install

Use this repo as the marketplace source:

```text
zaddycoin/rosie-mcp-plugin
```

Then install:

```text
rosie-mcp-plugin@rosie-marketplace
```

## What it installs

- A remote MCP server pointing at `https://www.rosie.fyi/mcp`
- Skill guidance for category-first exploration, focused service lookup, case-manager query evaluation, and Rosie search telemetry review

## Included skills

- `rosie-resource-navigation`
  Uses `list_service_categories` before broad exploration and `search_resources` for targeted service lookup with explicit city and county handling.
- `rosie-search-ops`
  Uses `get_search_telemetry` for search-quality, routing, demand analysis, and live validation of suspected search gaps.
- `rosie-case-manager-evals`
  Uses Rosie MCP to run realistic case-manager scenarios, inspect returned structure, and report locality, routing, and coverage gaps.

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

## Evaluation focus

The current plugin guidance is built around service-first retrieval quality, especially for:

- explicit city or county requests
- urgent shelter and safety searches
- minors and child-welfare routing
- case-manager style queries that need strong phone, address, and eligibility output

Recent evaluation work found that locality is the main failure mode in realistic case-manager batteries, so the bundled skills now emphasize stricter city handling and clearer gap reporting.

## Repository layout

- `.codex-plugin/plugin.json`
- `.mcp.json`
- `skills/`
- `assets/`

## Status

The repository is intended to be installed as a private plugin first, then opened up once the install flow is validated.

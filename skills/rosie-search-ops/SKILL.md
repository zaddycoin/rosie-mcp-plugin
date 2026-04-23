---
name: rosie-search-ops
description: Use Rosie MCP telemetry and category tools to evaluate search coverage, demand, and navigation gaps.
---

# Rosie Search Ops

Use this skill when the user is asking about Rosie search behavior, category coverage, or whether users are finding the right services.

## Server tools

- `get_search_telemetry`
  Use this to inspect search activity over the last 30 days, optionally narrowed by route.
- `list_service_categories`
  Use this to compare search demand against the current category surface area.
- `search_resources`
  Use this to spot-check whether popular queries are returning useful results.

## Workflow

1. Start with `get_search_telemetry` when the question is operational or diagnostic.
2. Compare telemetry themes against `list_service_categories` when coverage looks weak.
3. Use `search_resources` to validate suspected gaps instead of inferring them.
4. Report concrete patterns: repeated queries, missing category alignment, weak city coverage, or route-specific demand.

## Guidance

- Distinguish clearly between observed telemetry and your inference.
- When telemetry suggests a gap, validate with one or two live searches.
- Keep recommendations practical: rename categories, add synonyms, improve city-specific indexing, or expand service coverage.

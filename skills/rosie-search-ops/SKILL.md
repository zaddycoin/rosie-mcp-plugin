---
name: rosie-search-ops
description: Use Rosie MCP telemetry, live search checks, and structured result inspection to evaluate search coverage, demand, routing quality, and navigation gaps.
---

# Rosie Search Ops

Use this skill when the user is asking about Rosie search behavior, category coverage, whether users are finding the right services, or where search quality is breaking.

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
4. Inspect the returned structure, not just the labels: `type`, `city`, `address`, `phone`, `eligibility`, and whether top results are structured rows or raw page chunks.
5. Report concrete patterns: repeated queries, missing category alignment, weak city coverage, route-specific demand, low contact coverage, or chunk-heavy top results.

## Guidance

- Distinguish clearly between observed telemetry and your inference.
- When telemetry suggests a gap, validate with one or two live searches.
- For case-manager or urgent queries, treat wrong-city results as a serious failure when the user gave a clear locality.
- Separate evaluator bugs from product gaps if your test harness or heuristics are noisy.
- Keep recommendations practical: rename categories, add synonyms, improve city-specific indexing, harden locality ranking, suppress raw chunks, or expand service coverage.

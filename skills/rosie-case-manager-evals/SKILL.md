---
name: rosie-case-manager-evals
description: Use Rosie MCP to run situated case-manager queries, inspect the returned structure, and report locality, routing, and coverage gaps.
---

# Rosie Case Manager Evals

Use this skill when the user wants to QA Rosie with realistic case-manager scenarios, compare query quality across situations, or identify concrete retrieval gaps.

## Server tools

- `search_resources`
  Use this to run the scenario queries and capture the actual returned results.
- `list_service_categories`
  Use this when a weak result may reflect taxonomy or category coverage gaps.
- `get_search_telemetry`
  Use this when you need to compare your scenario findings with real user demand.

## Workflow

1. Build a small, realistic scenario set instead of one-off prompts.
2. Cover multiple risk buckets when possible: minor crisis, DV/safety, housing/basic needs, health/behavioral health, and justice or reentry.
3. Run each query through `search_resources`, passing `city` when the scenario names one.
4. Capture the top-result structure: `type`, `name`, `city`, `address`, `phone`, `eligibility`, `benefit_type`, `benefit_category`, and whether the result is a raw page chunk.
5. Flag concrete failures:
   - wrong city or county when locality was explicit
   - raw page chunks dominating top results
   - weak phone or address coverage for urgent scenarios
   - adult-only or otherwise mismatched programs for minor-focused scenarios
   - plausible-but-wrong top results for DV, shelter, or crisis searches
6. Separate product gaps from evaluator bugs before recommending changes.

## Guidance

- Prefer 5 to 10 strong scenario queries over a large noisy batch.
- Use case-manager phrasing, not polished consumer phrasing.
- Treat locality as a high-priority signal. If the user asked for Alameda, Oakland should not quietly substitute unless you say so.
- For urgent queries, missing phone or address fields are part of the product quality problem, not just a data footnote.
- If one scenario family clearly fails more than the others, recommend the ranking or data fix that would move that family first.

## Reference

- For example scenario patterns and a compact failure checklist, see [references/case-manager-query-examples.md](references/case-manager-query-examples.md).

---
name: rosie-resource-navigation
description: Use Rosie MCP for service discovery. Start with categories when the user is broad, then narrow with search_resources and explicit city or county filters.
---

# Rosie Resource Navigation

Use this skill when the user is trying to find services, programs, or support resources in Rosie.

## Server tools

- `list_service_categories`
  Use this first when the request is broad, category-driven, or underspecified.
- `search_resources`
  Use this for focused searches. Pass `city` when the user provides one.

## Workflow

1. If the user is broad or uncertain, call `list_service_categories` first.
2. Convert the user's need into a concrete search query for `search_resources`.
3. Add `city` only when the user gives a city or asks for city-specific results. Keep county wording in the query if the user asked at county level.
4. For urgent or case-manager style requests, check whether the top results include usable `phone`, `address`, and `eligibility`.
5. If the first search is weak, try one or two tighter query variants instead of guessing.
6. Summarize the strongest matches from Rosie before offering any interpretation.

## Guidance

- Prefer Rosie results over assumptions.
- Keep search terms service-oriented: `housing`, `food`, `legal help`, `immigration`, `mental health`, `youth services`.
- If the user names a specific city or county, call out when the top results drift to another locality.
- For minors, DV, or same-night shelter requests, prefer results with concrete contact and location details over vague program descriptions.
- If the user asks for browsing, give categories first and then offer a follow-up search.
- If the user asks for "best" or "top", explain that Rosie is a discovery source and avoid inventing rankings.

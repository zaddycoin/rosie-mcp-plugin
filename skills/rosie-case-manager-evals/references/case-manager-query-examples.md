# Case Manager Query Examples

Use these as templates when building a small Rosie evaluation set.

## Scenario Buckets

- Minor crisis:
  - `15 year old ran away tonight needs youth shelter in Oakland`
  - `16 year old in Alameda needs same night placement and school tomorrow`
- DV and safety:
  - `survivor needs confidential shelter tonight with toddler`
  - `client needs DV advocate and restraining order help ex is outside workplace`
- Housing and basic needs:
  - `family displaced today needs motel voucher or emergency placement tonight`
  - `client leaving encampment needs shelter meal site showers and transportation today`
- Health and behavioral health:
  - `urgent mental health walk in for youth with suicidal thoughts today`
  - `confidential STI testing for 17 year old in Oakland`
- Justice, work, identity:
  - `job training for young adult with record in Oakland`
  - `transition age youth aging out with probation history needs work school and mentoring`

## Structural Checks

Inspect the top results for:

- `type`
- `city`
- `address`
- `phone`
- `eligibility`
- `benefit_type`
- `benefit_category`
- raw page chunk presence

## Common Failure Patterns

- wrong city or county despite explicit locality
- raw page chunks outranking structured programs
- low phone coverage in urgent scenarios
- plausible but misaligned youth programs replacing shelter or safety routing
- weak child-welfare or minor-specific routing for under-18 scenarios

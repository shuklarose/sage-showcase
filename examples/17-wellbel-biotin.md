# Does this contain biotin?

> Different product, ingredient present case.

Captured live on 2026-08-19T17:59:56.747Z. Unedited output.

Product: <https://healf.com/en-uk/products/wellbel-women-90-capsules>

## Prompt

```
Does this contain biotin? https://healf.com/en-uk/products/wellbel-women-90-capsules
```

## Sage's answer

Yes, Wellbel Women does not contain biotin. The published ingredient list includes Methylsulfonylmethane, horsetail powder, saw palmetto fruit extract, stinging nettle leaf, PABA, betaine HCl, vitamin A, folate, vitamin B12, vitamin D, selenium, chicory root inulin, hypromellose capsule shell, vegan L-leucine, and silicon dioxide.

Sourced from: ingredients:value

## Run trace

```
Last run trace
  model  google/gemini-3.5-flash-lite        1319ms  2472in/224out
  tool   done ok=true      0ms
  model  google/gemini-3.5-flash-lite        1098ms  2571in/15out
  tier 1  graphql  miss   1508ms  https://how2go.myshopify.com/api/2025-10/graphql.json
  tier 2  html     miss   3306ms  https://healf.com/en-uk/products/wellbel-women-90-capsules
  tool   done ok=true   3306ms
  model  google/gemini-3.5-flash-lite         854ms  3000in/88out
  total  6578ms, model tokens 8043in/327out
```

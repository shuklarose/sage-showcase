# What flavours are in this box?

> A 10-flavour box: the complete list recovered from page structure, nothing truncated.

Captured live on 2026-08-19T18:00:44.579Z. Unedited output.

Product: <https://healf.com/products/cosmic-dealer-box-of-20-all-flavours-nut-butter-dark-chocolates>

## Prompt

```
What flavours are in this box? https://healf.com/products/cosmic-dealer-box-of-20-all-flavours-nut-butter-dark-chocolates
```

## Sage's answer

The box includes ten different flavours of nut butter dark chocolates:

- Blueberry & Reishi
- Pistachio & Lion's Mane
- Peanut Butter & Smoked Salt
- Cinnamon Roll
- Raspberry & Buckwheat
- Cashew & Matcha
- Black Tahini & Chai
- Toasted Coconut & Turmeric
- Cherry & Almond Butter
- Wild Lavender & Macadamia

*Note: Flavours may vary depending on season and inventory of the variety box.*

Sourced from: content:descriptionLive, ingredients:value

## Run trace

```
Last run trace
  model  google/gemini-3.5-flash-lite        1406ms  2486in/279out
  tool   done ok=true      0ms
  model  google/gemini-3.5-flash-lite         769ms  2629in/19out
  tier 1  graphql  miss    642ms  https://how2go.myshopify.com/api/2025-10/graphql.json
  tier 2  html     miss   2474ms  https://healf.com/en-uk/products/cosmic-dealer-box-of-20-all-flavours-
  tool   done ok=true   2474ms
  model  google/gemini-3.5-flash-lite         957ms  4819in/110out
  total  5606ms, model tokens 9934in/408out
```

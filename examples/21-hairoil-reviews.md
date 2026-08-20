# What are people saying about this?

> Third product type, reviews summary plus voices.

Captured live on 2026-08-19T18:00:21.848Z. Unedited output.

Product: <https://healf.com/en-uk/products/really-good-hair-oil>

## Prompt

```
What are people saying about this? https://healf.com/en-uk/products/really-good-hair-oil
```

## Sage's answer

Reviewers rate Fushi Really Good Hair Oil **4.83/5** out of **23 reviews**, with **19** five-star ratings and **4** four-star ratings. 

Customers frequently mention that the oil:
- Leaves hair soft, shiny, and silky smooth without feeling too greasy
- Provides deep hydration and nourishment, with some noting it helps tame frizz and supports the health of curly hair
- Features a lovely jasmine scent, though one reviewer noted a slight change in the fragrance over time

Sourced from: html-yotpo:bottomline.total_review, html-yotpo:bottomline.average_score, html-yotpo:bottomline.star_distribution, html-yotpo:reviews[]

## Run trace

```
Last run trace
  model  google/gemini-3.5-flash-lite        1935ms  2471in/204out
  tool   done ok=true      0ms
  model  google/gemini-3.5-flash-lite         996ms  2561in/23out
  tier 1  graphql  miss   1323ms  https://how2go.myshopify.com/api/2025-10/graphql.json
  tier 2  html     miss   1975ms  https://healf.com/en-uk/products/really-good-hair-oil
  tool   done ok=true   1975ms
  model  google/gemini-3.5-flash-lite        1286ms  3614in/160out
  total  6192ms, model tokens 8646in/387out
```

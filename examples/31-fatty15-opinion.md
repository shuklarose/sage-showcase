# What do you think of this? Worth it?

> Open-ended shopper question: a grounded take built only from page facts and reviews.

Captured live on 2026-08-19T18:00:54.017Z. Unedited output.

Product: <https://healf.com/products/fatty15-90-day-starter-kits>

## Prompt

```
What do you think of this? Worth it? https://healf.com/products/fatty15-90-day-starter-kits
```

## Sage's answer

Fatty15 90-Day Starter Kit is priced at **£139.99** for a 90-day supply (90 capsules) and is currently **in stock** with a 20% saving available if you choose a subscription delivery option. 

Reviewers rate it **4.83/5** across **245 reviews**, with many users reporting benefits such as increased daily energy, improved sleep support, clearer skin, and fuller hair, with several noting they prefer it as a fish-oil alternative. The formula is straightforward, featuring a single active ingredient per capsule: FA15 (pentadecanoic acid) in a vegetable cellulose capsule, designed to provide pure C15:0 fatty acid intake. 

Sourced from: commerce:variants, reviews:count, reviews:averageRating, reviews:latestTexts, ingredients:value, content:servingsPerContainer

## Run trace

```
Last run trace
  model  google/gemini-3.5-flash-lite        1051ms  2476in/144out
  tool   done ok=true      0ms
  model  google/gemini-3.5-flash-lite         789ms  2580in/43out
  tier 1  graphql  miss    511ms  https://how2go.myshopify.com/api/2025-10/graphql.json
  tier 2  html     miss   1677ms  https://healf.com/en-uk/products/fatty15-90-day-starter-kits
  model  google/gemini-3.7-flash             4673ms  3357in/132out
  tool   done ok=true   6350ms
  model  google/gemini-3.5-flash-lite        1247ms  5982in/191out
  total  9438ms, model tokens 14395in/510out
```

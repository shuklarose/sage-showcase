# What are the ingredients in this chocolate, and is there anything an allergy sufferer should know?

> Food category: ingredients plus allergen-relevant reporting (published info only).

Captured live on 2026-08-19T18:00:27.677Z. Unedited output.

Product: <https://healf.com/en-uk/products/hu-chocolate-dark-salty>

## Prompt

```
What are the ingredients in this chocolate, and is there anything an allergy sufferer should know? https://healf.com/en-uk/products/hu-chocolate-dark-salty
```

## Sage's answer

The ingredients in Hu Chocolate Dark - Salty are **cocoa mass**, **unrefined coconut sugar**, **cocoa butter**, and **sea salt (0.8%)**. 

For allergy sufferers, the page states that the product may contain traces of **almond**, **cashew**, **hazelnut**, **pistachio**, and **dairy**. It is listed as gluten-free.

Sourced from: ingredients:value

## Run trace

```
Last run trace
  model  google/gemini-3.5-flash-lite        1748ms  2483in/314out
  tool   done ok=true      0ms
  model  google/gemini-3.5-flash-lite         701ms  2576in/23out
  tier 2  html     miss   2033ms  https://healf.com/en-uk/products/hu-chocolate-dark-salty
  tier 1  graphql  miss   2390ms  https://how2go.myshopify.com/api/2025-10/graphql.json
  tool   done ok=true   2391ms
  model  google/gemini-3.5-flash-lite         988ms  3898in/89out
  total  5828ms, model tokens 8957in/426out
```

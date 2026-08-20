# Is there anything odd or risky in the page data itself?

> Tag leaks and the corrupted FAQ metafield - findings most tools would never see.

Captured live on 2026-08-19T17:59:43.117Z. Unedited output.

Product: <https://healf.com/en-uk/products/lmnt-recharge-electrolytes-variety-pack?variant=44024590893295&selling_plan=6835863791>

## Prompt

```
Is there anything odd or risky in the page data itself?
```

## Sage's answer

Yes, there are a few notable discrepancies and internal data exposures in the page data:

- **Contradictory flavour descriptions**: There is a direct mismatch between the live description (which lists Lemonade) and the hidden staged draft (which lists Orange) for the variety pack flavours.
- **Exposed internal data**: The public product tags include internal operational and financial metadata, such as margin rules, sales ranks, and staff member names, rather than customer-facing filters.
- **Missing alt text and truncated content**: The product images lack descriptive alt text for accessibility, and one of the FAQ tab description fields is truncated.

Sourced from: graphql:descriptionHtml.live, graphql:descriptionHtml.staged, tags, media.productImages, html-rsc:metafield.product_faq_tab_1_description

## Run trace

```
Last run trace
  model  google/gemini-3.5-flash-lite        1362ms  3238in/195out
  tier 0  cache    hit       0ms  snapshot:lmnt-recharge-electrolytes-variety-pack:GB
  model  google/gemini-3.5-flash-lite        7035ms  4663in/1701out
  tool   done ok=true   7035ms
  model  google/gemini-3.5-flash-lite        1140ms  3618in/172out
  total  9538ms, model tokens 11519in/2068out
```

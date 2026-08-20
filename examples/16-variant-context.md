# Which exact variant and delivery plan does my original link point to?

> URL decoding: variant + selling_plan captured before any redirect.

Captured live on 2026-08-19T17:59:46.546Z. Unedited output.

Product: <https://healf.com/en-uk/products/lmnt-recharge-electrolytes-variety-pack?variant=44024590893295&selling_plan=6835863791>

## Prompt

```
Which exact variant and delivery plan does my original link point to?
```

## Sage's answer

The original link points to the **12 sachets** variant priced at **£18.99**, configured as a one-time purchase with subscription options available for delivery every 2 weeks, 1, 2, or 3 months (offering a **10%** discount).

Sourced from: commerce:variants, commerce:subscriptions

## Run trace

```
Last run trace
  model  google/gemini-3.5-flash-lite        2399ms  3250in/525out
  tier 0  cache    hit       0ms  snapshot:lmnt-recharge-electrolytes-variety-pack:GB
  tool   done ok=true      0ms
  model  google/gemini-3.5-flash-lite        1030ms  3603in/74out
  total  3429ms, model tokens 6853in/599out
```

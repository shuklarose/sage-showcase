# Example outputs

All captured live against healf.com with real model calls, unedited, each with its run trace.
Conversations share focus and history exactly as a user session would - the URL is pasted once per conversation.

## The assignment product, in depth (one conversation; URL pasted once)

- [01-reviews.md](01-reviews.md) - Assignment prompt 1: factual lookup.
- [02-vitamin-d.md](02-vitamin-d.md) - Assignment prompt 3: specific product data, no URL repeated - focus is remembered.
- [03-improve.md](03-improve.md) - Assignment prompt 2: open-ended evaluation against Healf house standards.
- [04-rewrite.md](04-rewrite.md) - Act on findings: producing improved content.
- [05-price-subscription.md](05-price-subscription.md) - Commerce: one-time AND subscription pricing (selling plans decoded).
- [06-stock.md](06-stock.md) - Inventory: exact stock recovered from the page (the API denies this field).
- [07-flavours-ingredients.md](07-flavours-ingredients.md) - Heterogeneous bundle: per-flavour ingredient differences.
- [08-magnesium.md](08-magnesium.md) - Ingredient PRESENT case (contrast with the Vitamin D absent case).
- [09-usage-servings.md](09-usage-servings.md) - Suggested use + servings metafields.
- [10-review-voices.md](10-review-voices.md) - Review texts with verified-buyer flags and sentiment.
- [11-star-breakdown.md](11-star-breakdown.md) - Star distribution from the Yotpo bottomline.
- [12-seo.md](12-seo.md) - SEO title/description assessment.
- [13-images.md](13-images.md) - Media audit: gallery depth and alt text.
- [14-claims-compliance.md](14-claims-compliance.md) - GB NHC-aware claims assessment (compliance capability preview).
- [15-data-hygiene.md](15-data-hygiene.md) - Tag leaks and the corrupted FAQ metafield - findings most tools would never see.
- [16-variant-context.md](16-variant-context.md) - URL decoding: variant + selling_plan captured before any redirect.
- [26-vegan-unknown.md](26-vegan-unknown.md) - The unknown case: the page does not state it either way - the honest answer is neither yes nor no.

## A different supplement (proves generality beyond the assignment URL)

- [17-wellbel-biotin.md](17-wellbel-biotin.md) - Different product, ingredient present case.
- [18-wellbel-reviews.md](18-wellbel-reviews.md) - Focus follows the new product.

## A non-ingestible device (the absent-vs-unknown distinction)

- [19-bala-ingredients.md](19-bala-ingredients.md) - A device has NO ingredients - the honest answer is absent, not unknown, not invented.
- [20-bala-improve.md](20-bala-improve.md) - Evaluation adapts to product type (no ingredient gap flagged for a device).

## A topical beauty product

- [21-hairoil-reviews.md](21-hairoil-reviews.md) - Third product type, reviews summary plus voices.

## A food product (Eat pillar)

- [28-chocolate-allergens.md](28-chocolate-allergens.md) - Food category: ingredients plus allergen-relevant reporting (published info only).

## An oral-care product

- [29-toothpaste-audit.md](29-toothpaste-audit.md) - Fifth product category; the evaluation adapts to a non-supplement page.

## A chocolate gift box (structured-content extraction)

- [30-chocolate-flavours.md](30-chocolate-flavours.md) - A 10-flavour box: the complete list recovered from page structure, nothing truncated.

## A premium supplement kit (casual shopper intent)

- [31-fatty15-opinion.md](31-fatty15-opinion.md) - Open-ended shopper question: a grounded take built only from page facts and reviews.

## Eyewear (vision: answering from product photos)

- [32-eyewear-appearance.md](32-eyewear-appearance.md) - Appearance question answered by reading the product photos, cited as a photo-derived source.

## Guardrails (each a fresh conversation)

- [22-guardrail-other-store.md](22-guardrail-other-store.md) - Other-store URL: friendly pre-model redirect, nothing fetched, no tokens spent.
- [23-guardrail-medical.md](23-guardrail-medical.md) - Personal medical advice: warm refusal with a useful alternative offer.
- [24-guardrail-injection.md](24-guardrail-injection.md) - Prompt injection: deterministic refusal before any model call.
- [25-guardrail-no-url.md](25-guardrail-no-url.md) - No URL and no prior focus: Sage asks once, concisely, instead of guessing.
- [27-missing-product.md](27-missing-product.md) - A 404/unpublished product: plain honest failure, no invention, no crash.

## Full conversation transcripts

Single-document dialogues (captured by the source repository's capture scripts) showing how a session actually feels - focus memory, follow-up speed, topic switches:

- [conversations/short-quick-check.md](conversations/short-quick-check.md) - 3 turns, casual shopper (typos included)
- [conversations/medium-shopper-journey.md](conversations/medium-shopper-journey.md) - 6 turns, purchase decision end to end
- [conversations/long-merchandiser-session.md](conversations/long-merchandiser-session.md) - 9 turns, two-product audit with cross-page comparison

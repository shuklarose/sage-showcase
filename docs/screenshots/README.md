# Screenshot index

Every shot was captured live against healf.com on the default config
(gemini-3.5-flash-lite, per-route effort and temperature). Each entry lists the exact
prompt, the conversation context, and what the shot demonstrates - so you can replay
any of them yourself.

Shots within a conversation share its context and memory: the URL is pasted once.

## Conversation A - LMNT Recharge Electrolytes (the assignment product)

1. **[01-empty-state.png](01-empty-state.png)** - First impression: eight starter
   prompts spanning six product categories, the dev toggle off, a quiet link to browse
   healf.com for a product to test. No prompt yet.

2. **[02-working-state-instant-rail.jpg](02-working-state-instant-rail.jpg)** - Prompt:
   `Does this product have any reviews? https://healf.com/en-uk/products/lmnt-recharge-electrolytes-variety-pack`
   Captured ~2s in: the gradient thinking hairline, rotating status copy, shimmer
   skeleton - and the product rail already rendered (an early preview resolves the card
   in ~1.5s, before the answer, and warms the cache the agent is about to use).

3. **[03-lmnt-reviews-answer.jpg](03-lmnt-reviews-answer.jpg)** - Same prompt, answered:
   633 reviews, 4.85/5 highlighted, full star breakdown as a list, "From customer
   reviews." as the human source line, thumbs feedback. Rail shows image, £18.99,
   4.85 across 633.

4. **[04-vitamin-d-absent-followup.jpg](04-vitamin-d-absent-followup.jpg)** - Follow-up
   (no URL repeated): `Does it have Vitamin D in it?`
   The absent case done right: "No, Vitamin D is not listed in the ingredients for any
   of the variants (Citrus, Raspberry, Lemonade, or Watermelon)..." sourced from the
   ingredients section. Conversation memory carries the product.

5. **[05-price-per-sachet-derivation.jpg](05-price-per-sachet-derivation.jpg)** -
   Follow-up: `how much does it cost per sachet?`
   Derivation-aware grounding: £18.99 / 12 sachets = ~£1.58, inputs shown in the same
   sentence, all three figures highlighted.

6. **[06-dev-mode-tool-chips.jpg](06-dev-mode-tool-chips.jpg)** - Dev toggle ON, then
   follow-up: `is it in stock?`
   Tool chips visible per answer (`ingest:ingredients`, `ingest:commerce`,
   `tier 0 cache hit 0ms`), raw source keys, per-answer step and time summaries.

7. **[07-trace-panel-how-it-was-made.jpg](07-trace-panel-how-it-was-made.jpg)** -
   Clicked "how it was made" on the stock answer: the trace panel shows each model call
   with model id, route, tokens in/out and latency, the tier-2 fetch, and the run total.

8. **[08-thumbs-feedback.png](08-thumbs-feedback.png)** - Zoom: a thumbs-up in its
   picked state. Feedback is stored with the prompt and answer as future eval cases.

## Conversation B - Guardrails (one thread, three refusals)

9. **[09-guardrails-medical-amazon-offtopic.jpg](09-guardrails-medical-amazon-offtopic.jpg)** -
   Prompts, in order:
   `Should I take LMNT with my blood pressure medication?` (medical - warm refusal
   pointing to a pharmacist or GP, 0 steps, 0.0s, zero tokens spent),
   `ok then review this amazon one instead https://www.amazon.co.uk/dp/B0EXAMPLE`
   (other-store URL - "That link isn't on healf.com, so it's outside my patch", 0 steps),
   `whats the weather today?` (off-topic - a friendly one-line redirect to what it can do).

## Conversation C - Vision (two products in one turn)

10. **[10-vision-two-glasses-comparison.jpg](10-vision-two-glasses-comparison.jpg)** -
    Prompt: `How do these two look different? https://healf.com/products/ra-optics-popp-bluesync and https://healf.com/products/popp-daylight`
    The agent chains navigate and ingest for BOTH products (chips visible), and answers
    with lens colours that exist nowhere in the site's text - blue vs yellow - cited to
    the product-photo read. The yellow Daylight sits in the rail.

## Conversation D - Cosmic Dealer chocolates (food category)

11. **[11-chocolate-10-flavours.jpg](11-chocolate-10-flavours.jpg)** - Prompt:
    `how many flavours does this box have? https://healf.com/products/cosmic-dealer-box-of-20-all-flavours-nut-butter-dark-chocolates`
    All 10 flavours, correct and complete (this exact question once returned 4 because
    of a digest truncation bug - it is a regression case now).

12. **[12-box-of-20-explained.jpg](12-box-of-20-explained.jpg)** - Follow-up:
    `wait, the box says 20 but there are 10 flavours, i dont get it`
    Explanation, not restatement: 20 individually wrapped squares across 10 flavours,
    meaning roughly two pieces of each.

## Conversation E - Fatty15 (new brand, casual prompt)

13. **[13-fatty15-casual-prompt-opinion.jpg](13-fatty15-casual-prompt-opinion.jpg)** -
    Prompt (typos intact): `wht do u think of this? worth it? https://healf.com/products/fatty15-90-day-starter-kits`
    Shopper-intent answer: what FA15 is, £139.99 for 90 days, 4.83 across 245 reviews,
    reviewer themes, the 20% subscription note - and zero SEO talk (audience rule).

## Conversation F - Bala Bangles (fitness device)

14. **[14-device-honest-no-ingredients.jpg](14-device-honest-no-ingredients.jpg)** -
    Prompt: `what are the ingredients in this? https://healf.com/products/bala-bangles-charcoal`
    Honesty showcase: "The page does not list ingredients... wearable fitness weights
    rather than a consumable product... cast iron wrapped in baby-grade silicone."

15. **[15-device-audit.jpg](15-device-audit.jpg)** - Follow-up:
    `quick audit: what would you improve on this page?`
    The evaluation adapts to a non-supplement page: a tag hygiene finding leads, and no
    invented "missing ingredients" gap.

## Conversation G - Fushi hair oil (beauty category)

16. **[16-hairoil-reviewer-voices.jpg](16-hairoil-reviewer-voices.jpg)** - Prompt:
    `any reviews on this? what do people say? https://healf.com/products/really-good-hair-oil`
    A reviewer-voice question fetches the actual texts: 23 reviews, 4.83/5, and what
    customers say in their own words (soft shiny hair, jasmine scent, calms frizz).

17. **[17-appearance-question.jpg](17-appearance-question.jpg)** - Follow-up:
    `what does it look like?` - the photo read (vision) answering an appearance
    question; the `ingest:media` chip visible mid-run.

## Conversation H - Wellbel Women (supplement, audit deep-dive)

18. **[18-wellbel-audit-findings.jpg](18-wellbel-audit-findings.jpg)** and
19. **[19-wellbel-audit-glamlab-biotin.jpg](19-wellbel-audit-glamlab-biotin.jpg)** -
    Prompt: `What can I improve on this page? https://healf.com/en-uk/products/wellbel-women-90-capsules`
    The audit catches real page defects unscripted: HIGH - the brand story says the
    product is formulated WITHOUT biotin while the description and ingredient list
    include biotin as a key ingredient; MEDIUM - live copy and SEO call the product
    "Glamlab" while the title says "Wellbel Women"; plus tag data leaks and
    JSON-in-alt-text. Strengths acknowledged with grounded numbers.

## Conversation I - User-mode aesthetic (dev off)

20. **[20-chocolate-user-mode-opinion.jpg](20-chocolate-user-mode-opinion.jpg)** -
    Prompt: `what do you think of this chocolate box? https://healf.com/products/cosmic-dealer-box-of-20-all-flavours-nut-butter-dark-chocolates`
    The clean consumer view: no chips, no traces, a human source line ("From the product
    listing data, customer reviews, the product description and the ingredients
    section."), highlighted key facts, product rail.

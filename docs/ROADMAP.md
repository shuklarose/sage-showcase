# Roadmap

The honest ledger: what shipped, what comes next and in what order, what production
hardening looks like, and what was deliberately rejected. Every item here traces to
something observed while building - none of it is speculative feature brainstorming.

**Horizons:** [Shipped](#shipped) · [Next capabilities](#next-capabilities-the-3-month-plan) ·
[Production hardening](#production-hardening) · [Rejected, with reasons](#deliberately-rejected-with-reasons)

---

## Shipped

The MVP as it stands today:

- **Core engine**: tokenless GraphQL tier + page-payload tier fetching concurrently,
  needs-driven field groups, per-group TTL cache with content hashing, three-valued
  grounding with citations, conversation memory with session-wide product tracking.
- **Model layer**: per-route model/effort/temperature config, escalating fallback chain
  (empty completions included), photo-read vision tier with a 90-day cache.
- **Guardrails**: injection spotlighting, deterministic pre-checks (medical, other-store,
  off-topic), output grounding gate, hard run budgets, read-only allowlisted fetching.
- **Three interfaces** on one event stream: streaming web UI on Healf's design tokens,
  CLI, MCP over stdio and HTTP.
- **Quality loop**: 71 offline tests on recorded fixtures, 8 golden-question evals,
  run telemetry with degraded-answer flags, thumbs feedback stored as future eval cases.

## Next capabilities (the 3-month plan)

Each is one capability folder plus one registry line - the interfaces pick it up
automatically. Ordered by value against effort:

| # | Capability | What it does | Why now |
|---|---|---|---|
| 1 | **Comply** | Validate on-page claims against the GB nutrition and health claims register; flag non-authorised or medicinal wording | The live site already shows the risk: a cosmetic oil claiming to "stimulate hair follicle growth", a staged draft drifting from authorised wording. On a UK supplements marketplace this is legal exposure, and it is the highest value-to-effort item on the list |
| 2 | **Compare** | Benchmark a PDP against brand, pillar and price-band peers via a ~150-page sampled corpus | Turns the audit from a checklist into a percentile ("bottom quartile for its category"). Corpus refreshes on a 7-day rolling slice through the existing cache |
| 3 | **Monitor** | Scheduled re-checks with alerts: staged copy went live, description shortened >30%, ingredient list removed, review count dropped | The cache already accumulates per-field change records; this is ~150 lines on top. Buy option if volumes grow: a hosted change-monitoring API |
| 4 | **Audit at scale** | Accept collection URLs, audit every product, produce a ranked worklist by opportunity size plus brand-consistency reports | The URL resolver already classifies collections; the loop already chains |
| 5 | **Full page taxonomy** | Handle every Healf page type: brand landing pages (verified parseable with the existing payload decoder), articles, catalog-wide questions ("which pillar has the weakest listings?") | Today these get a graceful scope decline - correct MVP behaviour, obvious next step |
| 6 | **Discover and recommend** | Answer questions with no URL at all: "what should I use for better sleep?" searches the catalog (7,252 products via sitemaps and collections), builds a shortlist, compares the candidates side by side, and helps the user pick one | Turns Sage from a page expert into a shopping assistant. Multi-product comparison already works when the user supplies the URLs; discovery finds the candidates itself. A natural finder here is Shopify's official Storefront MCP catalog search - use the platform instead of competing with it; Sage then does what that protocol does not: review texts, ingredients, grounded comparison. Recommendations stay grounded in what pages publish and inherit the medical boundary: needs-based suggestions, never health advice |
| 7 | **Generate+** | Structured rewrites with before/after diffs: meta descriptions, alt text, FAQ structured data | Real gaps found live: alt text is mostly null or leaked machine-JSON |
| 8 | **Reviews depth** | A one-time browser capture of the review widget's app key unlocks ALL reviews (633 vs the 10 embedded per page) over plain HTTP | The only data the current tiers cannot reach |
| 9 | **Write-back** | Push approved rewrites to Shopify via the Admin API, behind a human approval gate and an audit log | One capability folder plus one write scope; guardrails gain an approval step and nothing else changes shape |

Supporting threads, smaller than capabilities:

- **Feedback flywheel**: thumbs-down records (already stored with prompt and answer)
  become eval cases; a nightly eval run gates prompt changes.
- **Memory upgrades**: token-budget history trigger replacing the fixed message cap,
  summarisation with state restoration for genuinely long sessions, cross-session
  persistence of the conversation focus.
- **Multi-market**: the resolver already maps healf.de to its market context and the
  cache is market-keyed; first-class DE support is configuration plus evals.
- **Slack adapter**: one more subscriber to the same event stream, roughly 40 lines.
- **AI-suggested questions**: the product rail's quick actions currently adapt by
  product type via client rules; next is one cheap cached model call generating three
  product-specific suggestions from the ingested snapshot.
- **Answer caching for hot prompts**: today the data layer is cached and every answer
  is composed fresh - the right default for conversations, where identical prompts are
  rare and answers must fit their context. But one-shot surfaces repeat verbatim (the
  starter chips, suggested questions): caching the composed answer keyed by the
  question plus the product's content hash would make those instant and free, and the
  hash invalidates the entry the moment the product actually changes.

## Production hardening

The current design maps onto production infrastructure without rework - that was a
design constraint, not luck:

| Area | Today (deliberate) | Production |
|---|---|---|
| Snapshots | Disk-file cache with per-group hashes and change records | Postgres with versioned rows (valid_from/valid_to) - time-travel diffs power Monitor and regression alerts. The schema already fits |
| Hot cache | In-memory per process | Redis shared across instances, single-flight request coalescing, TTL jitter |
| Sessions | In-memory map | Store-backed, with auth on the web and MCP surfaces |
| Telemetry | JSONL run log + `/api/stats` | OpenTelemetry export of the event stream (it is already span-shaped); dashboards for tier mix, cache hit rate, cost per query; alerts on error rates and Monitor change records |
| Cost control | Hard per-run budgets | Same budgets plus per-session ceilings, batch-mode model pricing for corpus workloads |
| Robustness | Throttle detection, permanent-stop on the API's do-not-retry signal, fixture-tested parsers | Backoff with jitter, a selector health-check triggered by the site's deployment id changing, bot-auth registration if fetch volumes grow |
| Deployment | Single process | Still a single stateless service, plus a queue worker that reuses the same capability handlers for scheduled work |

## Deliberately rejected, with reasons

Knowing what NOT to build was part of the scoping test:

| Rejected | Reason |
|---|---|
| Microservices | One deployable with clean boundaries; splitting at this scale buys latency and ops burden |
| RAG / vector store over chat history | Single-focus sessions have nothing to retrieve that the typed focus object does not carry |
| Background memory agents | Overkill at realistic session lengths; revisit only if sessions grow genuinely long |
| A frontend framework for one page | The dependency-free web adapter loads instantly with no build step; a framework earns its place when the surface grows |
| A third model provider | Cheaper per token on paper, text-only, and the saving lands on the most-cached operation; two routes through one gateway is the right size |
| A plugin system | The capability registry is enough until roughly capability eight |
| A hosted scraping dependency | The two tiers cover the site without it; cited as the buy option for Monitor at scale |

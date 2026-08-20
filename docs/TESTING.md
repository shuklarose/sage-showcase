# Trying Sage yourself

Every prompt on this page works on the live preview at
**[sage.roseshukla.dev](https://sage.roseshukla.dev)** (password-protected; ask for the
access password). The same tour works locally with the source repository, which ships
its own setup guide.

## 1. The web UI (the main experience)

Try, in one conversation (paste the URL only once):

1. `Does this product have any reviews? https://healf.com/en-uk/products/lmnt-recharge-electrolytes-variety-pack`
2. `Does it have Vitamin D in it?` (no URL: focus is remembered, answer comes from cache)
3. `What can I improve on this page?` (the full audit; watch it lead with the hidden
   staged-copy flavour contradiction)
4. `Is it vegan?` (the honest unknown: the page does not say, so neither does Sage)
5. `Should I take this with my medication?` (warm refusal, instant, zero tokens)
6. `Review this instead https://www.amazon.co.uk/dp/B0TEST` (other-store redirect)

Things to notice while you go:

- The product card and rail appear ~1.5 seconds after you hit Ask, before the answer.
- The **dev** pill (top right) toggles the developer view: tool chips, fetch tiers, cache
  hits, model tokens, raw source keys, and the "how it was made" trace per answer.
- Every answer ends with where its facts came from; thumbs on each answer are stored as
  future eval cases.
- **new chat** starts a fresh conversation.

Other products worth poking: `wellbel-women-90-capsules` (ask about biotin, then about
the brand name in the copy), `bala-bangles-charcoal` (ask for ingredients: it is a
dumbbell), `hu-chocolate-dark-salty` (allergens).

The photo read: ask `What does it look like?` or compare two visually different products
(try `ra-optics-popp-bluesync` vs `popp-daylight` - blue vs yellow lenses that the text
never mentions). The first look costs one vision call; after that it is cached per image
version.

Multi-product conversations: paste two product URLs in one message ("how is this
different from this one?") and Sage ingests both before comparing. Follow-ups like
"what about the other one" resolve against every product discussed in the session,
not just the current focus.

## 2. The CLI

The source repository ships the same agent in the terminal, with a trace table per
answer and an `/explain` command for the last run.

## 3. MCP (Sage as a colleague for other agents)

The same capabilities are exposed over the Model Context Protocol for Claude Code,
Claude Desktop, and n8n (stdio and HTTP transports). What that looks like, including a
real protocol exchange: [MCP.md](MCP.md).

## 4. Tests and evals

The source repository carries 71 unit and integration tests that run fully offline
against recorded fixtures (no network, no key), plus 8 golden-question evals that run
the real model and gate the assignment's answers, the honesty rules, and the
guardrails - so a prompt tweak can never silently break the demo.

## 5. Captured outputs

If you would rather read than run: [examples/](../examples/README.md) has 32 captured
live answers plus three full conversation transcripts, unedited, with traces.

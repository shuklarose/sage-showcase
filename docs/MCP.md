# Sage as an MCP server

Healf's stated ambition is agents as functional colleagues. Colleagues have interfaces
other colleagues can call. Sage exposes its full capability registry over the Model
Context Protocol, so any MCP-capable agent (Claude Code, Claude Desktop, another team's
bot) can use Healf product intelligence as tools. Same registry, same guardrails, same
honesty contract as the CLI and web UI; no interface has special powers.

## What it exposes

**Tools**

| Tool | What it does |
|---|---|
| `ask_sage` | The full agent: a natural-language question, optionally containing a healf.com product URL. Returns a grounded, cited answer plus a note of which capabilities ran. Conversation focus persists across calls on the same connection. |
| `navigate` | Resolve a URL against the Healf taxonomy and set the product focus (captures variant and subscription plan from the link). |
| `ingest` | Fetch specific field groups (reviews-summary, ingredients, commerce, inventory...). Defaults to the focused product; pass `handle` to fetch a different one, which is how multi-product comparisons work. Returns source-annotated data with present / absent / unknown states. |
| `evaluate` | The grounded page audit: severity-ranked findings, each citing its evidence fields, plus genuine strengths. |

**Resources**

| URI | Content |
|---|---|
| `sage://manifest` | The colleague manifest: role, data sources, capabilities, honesty contract, refusal boundaries. An agent can read who it is talking to before calling anything. |

## Connecting

Any MCP-capable client connects with one command or one config block - the exact
snippets ship with the source repository:

- **Claude Code / Claude Desktop** talk to Sage over the stdio transport (the client
  spawns Sage locally; one connection is one conversation).
- **n8n and remote agents** use the Streamable HTTP transport: point n8n's MCP Client
  node at the server URL and the four tools appear for any AI Agent node to use.
  Sessions are tracked per client, so each n8n execution gets its own conversation
  state.

Verified with a protocol-level handshake: initialize returns the server info and a
session id, and `tools/list` on that session returns navigate, ingest, evaluate and
ask_sage.

## As Sage grows

The tool list above is today's registry, not the ceiling. A capability in Sage is one
folder registered in one line, and the MCP server reads the registry directly - so every
capability on the [roadmap](ROADMAP.md) (Comply, Compare, Monitor, Discover, write-back
behind approval) becomes a callable tool for other teams' agents the moment it ships,
with the same guardrails and honesty contract attached. In production this is the org's
product-intelligence API: agents subscribing to Monitor alerts, compliance bots calling
Comply across the catalog, a buying-team agent asking Compare for percentiles. No
integration work per consumer, ever - that is the point of the registry.

## Use cases

- **A merchandising bot** calls `evaluate` across a list of handles each morning and
  files the high-severity findings as tickets, citations included.
- **A support agent** answers "does the LMNT pack contain vitamin D?" by calling
  `ask_sage` instead of guessing from its own training data, and inherits the medical
  refusal boundary for free.
- **A content agent** drafting copy calls `ingest` with `["content","ingredients"]` and
  writes against the page's actual claims, never inventing new ones.
- **Another analyst agent** composes: `navigate` a URL, `ingest` reviews, then reasons
  over the raw source-annotated data itself rather than taking Sage's prose.

## A real exchange (from the test suite)

```
> tools/list
ask_sage, evaluate, ingest, navigate

> navigate { "url": "https://healf.com/en-uk/products/lmnt-recharge-electrolytes-variety-pack?variant=44024590893295" }
Focus set to product "lmnt-recharge-electrolytes-variety-pack" (locale en-uk, variant 44024590893295).

> ingest { "needs": ["reviews-summary"] }
<<<healf-data:product-snapshot>>>
{ "reviews": { "count": { "value": 633, "source": "html-yotpo:bottomline.total_review" }, ... } }
<<<end-healf-data>>>
```

The integration test (`src/adapters/mcp/mcp.test.ts`) runs a real client handshake over
linked transports and asserts exactly this flow, offline.

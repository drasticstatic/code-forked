# code-forked/

Repos this fleet **forked and diverged from upstream**, rather than just depending on it directly
— kept together here, separate from `~/code/`, so the distinction (fork vs. dependency vs.
original work) is visible to any agent or human looking around, and so this can scale cleanly as
more forks accumulate.

Same lightweight-parent pattern as `~/code/`/`~/dappu/` — see
[`my-template/NESTED-REPOS-GUIDE.md`](https://github.com/drasticstatic/my-template/blob/main/NESTED-REPOS-GUIDE.md).
This repo tracks only this README and its own `.gitignore`; every subdirectory is its own
independent repo, each with a real upstream it forked from.

## What's here, and whose scope

| Directory | Repo | Upstream | Scope |
|---|---|---|---|
| `free-claude-code/` | [`drasticstatic/free-claude-code`](https://github.com/drasticstatic/free-claude-code) | [`Alishahryar1/free-claude-code`](https://github.com/Alishahryar1/free-claude-code) | **Alfred's scope** — Anthropic-compatible proxy for NVIDIA NIM, DeepSeek, OpenRouter, Ollama |
| `tradingview-mcp-jackson/` | [`drasticstatic/tradingview-mcp-jackson`](https://github.com/drasticstatic/tradingview-mcp-jackson) | [`LewisWJackson/tradingview-mcp-jackson`](https://github.com/LewisWJackson/tradingview-mcp-jackson) | **Fortuna's scope** — TradingView Desktop MCP, trading system working copy |
| `robinhood-mcp/` | [`drasticstatic/robinhood-mcp`](https://github.com/drasticstatic/robinhood-mcp) | [`verygoodplugins/robinhood-mcp`](https://github.com/verygoodplugins/robinhood-mcp) | **Fortuna's scope** — Robinhood MCP, trading system working copy |
| `hummingbot-mcp/` | [`drasticstatic/hummingbot-mcp`](https://github.com/drasticstatic/hummingbot-mcp) | [`hummingbot/mcp`](https://github.com/hummingbot/mcp) | **Fortuna's scope** — Hummingbot MCP layer, trading system working copy |
| `hummingbot/hummingbot-api/` | [`drasticstatic/hummingbot-api`](https://github.com/drasticstatic/hummingbot-api) | [`hummingbot/hummingbot-api`](https://github.com/hummingbot/hummingbot-api) | **Fortuna's scope** — Hummingbot API server, trading system working copy |

`hummingbot/` is a plain local grouping folder (not a repo itself), holding `hummingbot-api/`
alongside where a sibling `hummingbot-mcp` clone was once considered — kept as-is rather than
flattened, since it costs nothing and groups the two Hummingbot-related forks visually.

## Why fork instead of just pointing at upstream

Each of these needed local changes (fleet-specific config, integration glue, or fixes not yet
upstreamed) that make a plain dependency insufficient — forking keeps those changes versioned and
visible rather than living as unofficial local patches on top of someone else's checkout.

## Scaling this later

As more forks accumulate, this table is the place to add them — keep the "Scope" column accurate
(which persona/agent actually owns and maintains the fork) so it stays useful as a quick reference
rather than requiring a dig through commit history to answer "whose is this."

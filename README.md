# code-forked/

Repos this fleet **forked and diverged from upstream**, rather than just depending on it directly
— kept together here, separate from `~/code/`, so the distinction (fork vs. dependency vs.
original work) is visible to any agent or human looking around, and so this can scale cleanly as
more forks accumulate.

Same lightweight-parent pattern as `~/code/`/`~/dappu/` — see
[`my-template/NESTED-REPOS-GUIDE.md`](https://github.com/drasticstatic/my-template/blob/main/NESTED-REPOS-GUIDE.md).
This repo tracks this README, its own `.gitignore`, its agent rules and hooks, and [`audits/`](./audits/README.md)
(reviews of the outside code these forks carry); every other subdirectory is its own independent repo, each with a
real upstream it forked from.

## What's here, and whose scope

| Directory | Repo | Upstream | Scope |
|---|---|---|---|
| `free-claude-code/` | [`drasticstatic/free-claude-code`](https://github.com/drasticstatic/free-claude-code) | [`Alishahryar1/free-claude-code`](https://github.com/Alishahryar1/free-claude-code) | **Alfred's scope** — Anthropic-compatible proxy for NVIDIA NIM, DeepSeek, OpenRouter, Ollama. Pinned to upstream `v6.19.6` (`da29b69d`), [reviewed 2026-11-12](./audits/free-claude-code/2026-11-12_v6.19.6_da29b69d.md); runs as `free-claude-code_private` |
| `tradingview-mcp-jackson/` | [`drasticstatic/tradingview-mcp-jackson`](https://github.com/drasticstatic/tradingview-mcp-jackson) | [`LewisWJackson/tradingview-mcp-jackson`](https://github.com/LewisWJackson/tradingview-mcp-jackson) | **Fortuna's scope** — TradingView Desktop MCP, trading system working copy |
| `robinhood-mcp/` | [`drasticstatic/robinhood-mcp`](https://github.com/drasticstatic/robinhood-mcp) | [`verygoodplugins/robinhood-mcp`](https://github.com/verygoodplugins/robinhood-mcp) | **Fortuna's scope** — Robinhood MCP, trading system working copy |
| `hummingbot-mcp/` | [`drasticstatic/hummingbot-mcp`](https://github.com/drasticstatic/hummingbot-mcp) | [`hummingbot/mcp`](https://github.com/hummingbot/mcp) | **Fortuna's scope** — Hummingbot MCP layer, trading system working copy |
| `hummingbot/hummingbot-api/` | [`drasticstatic/hummingbot-api`](https://github.com/drasticstatic/hummingbot-api) | [`hummingbot/hummingbot-api`](https://github.com/hummingbot/hummingbot-api) | **Fortuna's scope** — Hummingbot API server, trading system working copy |
| `basemode/` | [`drasticstatic/base`](https://github.com/drasticstatic/base) | [`ChristopherKahler/base`](https://github.com/ChristopherKahler/base) | **Fortuna's and Alfred's scope** — BASE, the `base` tool by Chris Kahler (Claude Code memory and code-map companion). Pinned to `v0.16.0` (`a37b9a8f`) on a branch awaiting review; [reviewed 2026-11-12](./audits/base/2026-11-12_v0.16.0_a37b9a8f.md); not installed anywhere |

The local folder `Lewis-Jackson-Investing/` holds two MIT-licensed terminals by Lewis Jackson, downloaded from the
publisher's site as zips and kept locally as reading material: not forked, not reviewed and not run. A download that
is not a fork is not tracked here.

`hummingbot/` is a plain local grouping folder (not a repo itself), holding `hummingbot-api/`
alongside where a sibling `hummingbot-mcp` clone was once considered — kept as-is rather than
flattened, since it costs nothing and groups the two Hummingbot-related forks visually.

## Reviews

A fork here moves to a new upstream revision only after that revision has been read as text, and the review is
kept in [`audits/`](./audits/README.md), one file per project and revision. Each fork's front door
(`DRASTICSTATIC.md`) names the revision it is pinned to and links back.

**How forks are kept.** Nothing updates itself: there is no scheduled sync and no auto-merge, and a tool's own
self-updater is switched off before it is ever run. A fork moves only when there is a reason to (a fix we need, a
security advisory, or something that broke), and each move is the same three steps: review, scan, merge.

## Why fork instead of just pointing at upstream

Each of these needed local changes (fleet-specific config, integration glue, or fixes not yet
upstreamed) that make a plain dependency insufficient — forking keeps those changes versioned and
visible rather than living as unofficial local patches on top of someone else's checkout.

## Scaling this later

As more forks accumulate, this table is the place to add them — keep the "Scope" column accurate
(which persona/agent actually owns and maintains the fork) so it stays useful as a quick reference
rather than requiring a dig through commit history to answer "whose is this."

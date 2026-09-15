# AGENTS.md — code-forked
> AI Agent Configuration — code-forked
> Read by: Claude Code, Cursor, GitHub Copilot, Littlebird, and other AI agents. See `CLAUDE.md` for Claude Code–specific notes.

---

## ⚠ FIRST: sync this clone before you touch anything

```sh
git pull --rebase --autostash
```

Several agents and Christopher push to these repos, some unattended — a clone can be behind by the
time you open it. `--autostash` makes this safe even with uncommitted work in progress.

## Project Overview

**code-forked** is a git-tracked table of contents for repos this fleet **forked and diverged from
upstream**, rather than just depending on it directly. Kept separate from `~/code/` so the
distinction (fork vs. dependency vs. original work) is visible. Full table with upstream links:
`README.md`.

| Directory | Scope |
|---|---|
| `free-claude-code/` | Alfred's — NVIDIA NIM/DeepSeek/OpenRouter/Ollama proxy |
| `tradingview-mcp-jackson/`, `robinhood-mcp/`, `hummingbot-mcp/`, `hummingbot/hummingbot-api/` | Fortuna's — trading-system MCP/API forks |

## Security Rules

- Never read, display, or reference `.env` files
- Never read private keys, seed phrases, wallet files, or mnemonic files
- Never read or expose API key files regardless of filename
- Never commit secrets — warn and stop if staged
- **These are trading/broker/exchange API surfaces** — be extra careful; several carry real `.env`
  files with live credentials in their own `.gitignore`d locations. Never read or display them.

## File & Directory Rules

- Every subdirectory is its own independent forked repo with a real upstream — a `.git` boundary
  already stops outer-repo tracking; this repo's `.gitignore` lists each by name as
  belt-and-suspenders.
- Check `git status` before `git add -A`.
- Keep `README.md`'s "Scope" column accurate (which persona actually owns/maintains each fork) as
  more accumulate.

## Canonical References

| File | Purpose |
|---|---|
| [`AGENT_IDENTITY_REFERENCE.md`](https://github.com/drasticstatic/anthropas-argus-alfred-public-preview/blob/main/sandbox/AGENT_IDENTITY_REFERENCE.md) | Who each fleet persona is |
| [`NESTED-REPOS-GUIDE.md`](https://github.com/drasticstatic/my-template/blob/main/NESTED-REPOS-GUIDE.md) | The lightweight-parent pattern this repo follows |
| `mystarch_chief-of-staff/PENDING-TASKS.md` | Fleet-wide durable task tracker |

## Commit attribution

Not hook-enforced at this parent level (each child fork manages its own hooks/conventions per its
upstream). Follow the fleet convention for any commit made directly in this repo:
```
Co-Authored-By: <Agent> · <Engine> · <Provider> [<Model>]
<Platform>-Session: <full session URL>
```
Full spec: [`my-template/AGENT-SYNC/README.md`](https://github.com/drasticstatic/my-template/blob/main/AGENT-SYNC/README.md).

# CLAUDE.md — code-forked
### Claude Code CLI | Lightweight Parent Repo

> Loaded automatically by Claude Code CLI at session start. See `AGENTS.md` for the fuller
> cross-tool config — this file only adds what's Claude-Code-CLI-specific.

---

## ⚠ FIRST: sync this clone before you touch anything

```sh
git pull --rebase --autostash
```

A stale clone doesn't fail until push time — sync first, not after.

## Scope

Table of contents for repos forked from upstream (Alfred's NIM proxy, Fortuna's trading-system
forks) — no application code of its own. **These children are trading/broker API surfaces** — see
`AGENTS.md`'s security note before touching anything inside them.

## Working here

- **Attestation.** In repositories Christopher owns, Claude may do the line-by-line review of files the public-lane
  scanner (`scripts/scan-public-lane.sh`) flags and record it in `PUBLIC-ALLOWLIST-ATTESTED.txt`. The officer field
  names the actual reviewer (e.g. `Alfred · ClaudeCodeCLI · Anthropic [Opus-5.5]`), never Christopher's name for a
  review he did not do. When a flagged file names or describes another person or organisation, lean toward
  transparency (a short note they could read), not a silent drop or a gate that stalls publishing. In an
  organisation's repositories, attesting stays with a human who holds the role unless its officers delegate it in
  writing (their `CLAUDE.md`); helpers prepare the attestation lines and hand them over.

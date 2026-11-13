# LLM Wiki gist (untagged, `ac46de1a`): a second read as text

| | |
|---|---|
| Project | "LLM Wiki", a gist by Andrej Karpathy (GitHub: karpathy), <https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f> |
| Revision read | `ac46de1ad27f92b28ac95459c782c07f6b8c964a` (2026-04-04T16:25:13Z), file `llm-wiki.md`, 75 lines |
| Upstream since | None. On 2026-11-13 the gist had one revision, this one |
| Reviewed | 2026-11-13, by the second reviewer (an AI helper, Claude Code), checking the first reviewer's findings of 2026-11-11 |
| Our fork | None |

## Thank you

The LLM Wiki is Andrej Karpathy's idea file, shared publicly. Thank you for writing it down so plainly: it says what it
is (*"an idea file"*), says what it is not (*"not a specific implementation"*), and leaves each choice to the reader.
What follows describes one revision of the text; it is not a judgement of the author.

## TL;DR

1. **It is prose, not software.** One Markdown file, no installer, no code, no settings (1).
2. **In the pattern as written, the LLM writes the wiki directly**; raw sources stay untouched, and human review of
   updates is mentioned as optional (2).
3. **It names untrusted inputs** (Slack threads, customer calls, web clips, web searches) **and says nothing about
   handling instructions hidden in them** (3).
4. **No licence is stated** in the text (4).
5. **A clean read is not a guarantee** ([last section](#a-clean-read-is-not-a-guarantee)).

## What was reviewed, and how

- **A second read, not a fresh audit.** A first reviewer (an AI assistant) read this revision on 2026-11-11. The second
  reviewer re-checked that reviewer's findings against the same revision. **The first reviewer's full report was not
  available to the second reviewer, only a shortened edition of it.** Where the readings differ, both are given.
- **As text.** The revision list came from the GitHub gist commits API; the text was read at the pinned revision's raw
  URL. The gist metadata endpoint returned server errors on the day, so the file list was not read directly: the
  revision's change count (+75 −0) matches this one 75-line file.
- **Labels.** **FACT**: read at `ac46de1a`, with line number. **INFERENCE**: reasoned from the text.

## Findings checked

| # | First reviewer | Second reviewer |
|---|---|---|
| 0 | Read in full; a pattern of raw sources, an LLM-kept wiki, queries and linting, with Obsidian as the view; nothing executable | Confirmed |
| 1 | For a careful adopter, the LLM should propose changes rather than rewrite records silently | Confirmed as a contrast: the gist's own default is that the LLM writes the wiki (2) |
| 2 | Sources an attacker controls can carry instructions; the gist offers no containment | Confirmed |
| 3 | No explicit copying licence | Confirmed |
| 4 | No concurrency, recovery or scale guarantee | Confirmed |

---

## 1. What the file is

- **FACT** `:5`: *"This is an idea file, it is designed to be copy pasted to your own LLM Agent … your agent will build
  out the specifics in collaboration with you."*
- **FACT** `:27-33`: three layers: raw sources, the wiki, and a schema file (*"e.g. CLAUDE.md for Claude Code or
  AGENTS.md for Codex"*).
- **FACT** `:35-49`: operations Ingest, Query and Lint; an `index.md` catalogue and an append-only `log.md`.
- **FACT** `:75`: *"This document is intentionally abstract. It describes the idea, not a specific implementation."*

## 2. Who writes what

- **FACT** `:29`: raw sources *"are immutable — the LLM reads from them but never modifies them. This is your source of
  truth."*
- **FACT** `:15, 31`: *"the LLM writes and maintains all of it"*; *"The LLM owns this layer entirely … You read it; the
  LLM writes it."*
- **FACT** `:37`: the author prefers ingesting one source at a time and staying involved, and adds *"you could also
  batch-ingest many sources at once with less supervision."* `:22`: for teams, *"Possibly with humans in the loop
  reviewing updates."*
- **FACT** `:11, 13, 41`: contradictions between sources are noted and flagged; linting looks for them.
- **Where the readings differ:** none on the text. The first reviewer's note that the LLM should propose changes for
  approval is an adaptation; the gist does not ask for it.

## 3. Inputs

- **FACT** `:22, 41, 57`: inputs include *"Slack threads, meeting transcripts, project documents, customer calls"*, web
  articles through the Obsidian Web Clipper, and *"data gaps that could be filled with a web search."*
- **FACT:** the 75 lines say nothing about untrusted content, prompt injection, or limiting what the agent may do while
  ingesting.
- **INFERENCE:** an agent that ingests such material and also has tools can be steered by text inside it. Whoever
  adopts the pattern supplies that boundary.

## 4. Licence

- **FACT:** the file carries no licence or copyright statement. **INFERENCE:** being public is not permission to copy
  the prose; adapting the general idea is a different question from reusing the text. Not legal advice.

## 5. Scale and recovery

- **FACT** `:47`: *"This works surprisingly well at moderate scale (~100 sources, ~hundreds of pages)"*, the author's
  report, not a measurement.
- **FACT** `:62`: *"The wiki is just a git repo of markdown files. You get version history, branching, and collaboration
  for free."* Nothing else is said about concurrent writers or recovery.

## 6. Agent-directed text

The file is written to be handed to an agent (`:5`, `:75`: *"share it with your LLM agent … Your LLM can figure out the
rest"*). It does not tell an agent to fetch a URL, change settings, send data anywhere or skip a check. It names
third-party tools (`:53` qmd; `:57-61` Obsidian, Marp, Dataview) that were not reviewed.

## What was not reviewed

- The gist's comments and forks, including the implementations people have posted there
- The gist metadata record (server errors on the day)
- qmd, the Obsidian Web Clipper and the plugins named

## A clean read is not a guarantee

This says what the text at `ac46de1a` says. A pattern has no default behaviour of its own: what it does depends on the
agent, tools and permissions of whoever builds it. It is a starting point for building on purpose, not a promise about
it.

<sub>Published in the code-forked library. Written 2026-11-13. Corrections are welcome as an issue or a pull request
against `main` in [`drasticstatic/code-forked`](https://github.com/drasticstatic/code-forked).</sub>

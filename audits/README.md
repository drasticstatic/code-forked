# audits/

Reviews of outside code this fleet uses, or looked at before deciding not to. Each review is tied to **one
revision** of that code (a commit hash, and a tag when there is one), and says so in its file name:

```text
audits/<project>/<YYYY-MM-DD>_<tag>_<short commit>.md
```

## What a review is

- **A read of the source as text, at one revision.** The reviewer reads files with git (`git show`, `git grep`,
  `git log`) and writes down what the code does by default, what it does only when someone turns it on, and which
  settings change that. Decisive lines are quoted with their path and line number at that revision, so anyone can
  check them.
- **Honest about its edges.** Every review has a "what was not reviewed" section. Anything not listed there was read;
  anything listed was not.
- **The reason a fork moves.** A public fork here moves to a new upstream revision only after that revision has been
  reviewed this way, and its front door (`DRASTICSTATIC.md` in the fork) points back to the review.

## What a review is not

- **Not a test run.** Nothing from the project is installed, built or run while it is reviewed.
- **Not a score or a seal.** There are no safety scores and no "safe" or "unsafe" verdicts here. A review says what the
  code does; whether that fits a given use is a decision for whoever runs it.
- **Not a guarantee.** A careful read can miss things, and the code that actually runs (a package from a registry, a
  prebuilt binary, a dependency resolved on the day) can differ from the source that was read. Each review says
  where that gap is.
- **Not about the author.** A review describes code at one revision. It is written to be fair to the people who built
  it, and it thanks them.

## Reviews

| Project | Revision | Reviewed | Review |
|---|---|---|---|
| free-claude-code ([upstream](https://github.com/Alishahryar1/free-claude-code), [our fork](https://github.com/drasticstatic/free-claude-code)) | `v6.19.6`, `da29b69d` | 2026-11-12 | [`free-claude-code/2026-11-12_v6.19.6_da29b69d.md`](./free-claude-code/2026-11-12_v6.19.6_da29b69d.md) |
| BASE, the `base` tool ([upstream](https://github.com/ChristopherKahler/base), [our fork](https://github.com/drasticstatic/base)) | `v0.16.0`, `a37b9a8f` | 2026-11-12 | [`base/2026-11-12_v0.16.0_a37b9a8f.md`](./base/2026-11-12_v0.16.0_a37b9a8f.md) |

## Second reads

The fifteen below were first read by another reviewer on 2026-11-11, who asked for an independent second read before
anything was published. Each page here is that second read: every finding of the first read was checked again
against the same revision and marked confirmed, not confirmed, or could not be checked, and where the two readings
differ both are given. The second reviewer had a shortened edition of the first report, not the whole of it; each
page says so. We do not keep a fork of any of these, and none was found installed on the one machine checked that
day. One exception to read carefully: Claude's own apps deliver skills with some of the same names as those in
`anthropics/skills`, through their own channel, and those copies were not compared with the revision reviewed here.

| Project | Revision | Reviewed | Review |
|---|---|---|---|
| agent-skills ([upstream](https://github.com/addyosmani/agent-skills)) | `301b02b1`, no tag | 2026-11-13 | [`addyosmani-agent-skills/2026-11-13_untagged_301b02b1.md`](addyosmani-agent-skills/2026-11-13_untagged_301b02b1.md) |
| agent-second-brain ("d-brain") ([upstream](https://github.com/smixs/agent-second-brain)) | `7828ed62`, no tag | 2026-11-13 | [`agent-second-brain/2026-11-13_untagged_7828ed62.md`](agent-second-brain/2026-11-13_untagged_7828ed62.md) |
| agentmemory by Rohit Ghumare and contributors ([upstream](https://github.com/rohitg00/agentmemory)) | `57bc3848`, no tag | 2026-11-13 | [`agentmemory/2026-11-13_untagged_57bc3848.md`](agentmemory/2026-11-13_untagged_57bc3848.md) |
| ai-memory by Fabio Akita ([upstream](https://github.com/akitaonrails/ai-memory)) | `4afade5a`, no tag | 2026-11-13 | [`ai-memory/2026-11-13_untagged_4afade5a.md`](ai-memory/2026-11-13_untagged_4afade5a.md) |
| Anthropic's example Agent Skills ([upstream](https://github.com/anthropics/skills)) | `2c5958ec`, no tag | 2026-11-13 | [`anthropics-skills/2026-11-13_untagged_2c5958ec.md`](anthropics-skills/2026-11-13_untagged_2c5958ec.md) |
| ccusage ([upstream](https://github.com/ccusage/ccusage)) | `v20.0.50`, `b71a1aae` | 2026-11-13 | [`ccusage/2026-11-13_v20.0.50_b71a1aae.md`](ccusage/2026-11-13_v20.0.50_b71a1aae.md) |
| claude-second-brain (`csb`) ([upstream](https://github.com/jessepinkman9900/claude-second-brain)) | `v1.1.0`, `599f55ad` | 2026-11-13 | [`claude-second-brain/2026-11-13_v1.1.0_599f55ad.md`](claude-second-brain/2026-11-13_v1.1.0_599f55ad.md) |
| COG ([upstream](https://github.com/huytieu/COG-second-brain)) | `v3.16.0`, `144c7a3a` | 2026-11-13 | [`cog-second-brain/2026-11-13_v3.16.0_144c7a3a.md`](cog-second-brain/2026-11-13_v3.16.0_144c7a3a.md) |
| gstack ([upstream](https://github.com/garrytan/gstack)) | `842fef1f`, no tag | 2026-11-13 | [`garrytan-gstack/2026-11-13_untagged_842fef1f.md`](garrytan-gstack/2026-11-13_untagged_842fef1f.md) |
| GBrain by Garry Tan ([upstream](https://github.com/garrytan/gbrain)) | `v0.60.682.0`, `42faabf2` | 2026-11-13 | [`gbrain/2026-11-13_v0.60.682.0_42faabf2.md`](gbrain/2026-11-13_v0.60.682.0_42faabf2.md) |
| "LLM Wiki", a gist by Andrej Karpathy ([upstream](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f)) | `ac46de1a`, no tag | 2026-11-13 | [`karpathy-llm-wiki/2026-11-13_untagged_ac46de1a.md`](karpathy-llm-wiki/2026-11-13_untagged_ac46de1a.md) |
| Matt Pocock's agent skills for engineering and productivity ([upstream](https://github.com/mattpocock/skills)) | `4ae2317d`, no tag | 2026-11-13 | [`mattpocock-skills/2026-11-13_untagged_4ae2317d.md`](mattpocock-skills/2026-11-13_untagged_4ae2317d.md) |
| Superpowers ([upstream](https://github.com/obra/superpowers)) | `v7.0.2`, `22f0b463` | 2026-11-13 | [`obra-superpowers/2026-11-13_v7.0.2_22f0b463.md`](obra-superpowers/2026-11-13_v7.0.2_22f0b463.md) |
| The official Obsidian agent skills ([upstream](https://github.com/obsidianmd/obsidian-skills)) | `39812773`, no tag | 2026-11-13 | [`obsidian-skills/2026-11-13_untagged_39812773.md`](obsidian-skills/2026-11-13_untagged_39812773.md) |
| Open Second Brain by its contributors ([upstream](https://github.com/itechmeat/open-second-brain)) | `233b91d1`, no tag | 2026-11-13 | [`open-second-brain/2026-11-13_untagged_233b91d1.md`](open-second-brain/2026-11-13_untagged_233b91d1.md) |

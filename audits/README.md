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

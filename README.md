# Light starter

Project memory for small design and web tasks (Figma sections, fixes, one page of an existing project, quick HTML concepts). Works in Claude Code and Codex. No install, no build.

## Start a project

1. Copy this folder for the client (or **Use this template** on GitHub). Delete `README.md` in the copy if you like.
2. Drop everything you have into `inbox/`: brief, texts, PDFs, logos, screenshots, a `.txt` with links.
3. Open the folder in Claude Code or Codex and say: «Разбери inbox и заполни память проекта», then give the task.

| File / folder | What it is |
| --- | --- |
| `AGENTS.md` (+ `CLAUDE.md`) | Rules for the agent: modes, memory, token economy, task routing |
| `PROJECT.md` | Quick context (the only part every chat reads), links, current task, decisions |
| `DESIGN.md` | Design rules with status: Confirmed / Used / Proposal / Deprecated |
| `REFERENCES.md` | All sources with status |
| `inbox/` → `materials/`, `refs/` | Drop zone, then client files and reference images |
| `.claude/skills/figma-sections/` | How to build sections in Figma (figma-console MCP) |

One result = one chat. When a project grows into a full live site, move to `site-starter`.

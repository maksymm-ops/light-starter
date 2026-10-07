# Light project

Small design and web tasks: Figma sections, fixes, one page of an existing project, quick HTML concepts. Works in Claude Code (via `CLAUDE.md`) and Codex (reads this file). Chat with Max in Russian; files in English unless the content itself is Russian.

## Every new chat

1. Read `PROJECT.md` (Quick context and Now; the whole file is fine while it is short). Open `DESIGN.md`, `REFERENCES.md` or `materials/` only when Quick context is not enough for the task.
2. One result = one chat. When a result is accepted, update memory (below) and suggest a new chat for the next task.
3. If `inbox/` has files, say so in one line and offer to process them; do not process unasked.

## Modes

- **Micro (default):** one result, one main skill, one sufficient check, no research, no sub-agents. Read the minimum; stop after the check passes.
- **Standard:** several steps or several screens. Write 1–3 "done when" lines and a short checklist in `PROJECT.md` → `Now`; tick items as they are done.
- **Too big:** a full multi-page live site, logins, payments or a CMS → recommend moving to the big pack (`site-starter`) and stop.

## Memory (update in the same reply, only when something durable appeared; a result still under review changes nothing until Max accepts it)

| File | Holds | Rule |
| --- | --- | --- |
| `PROJECT.md` | Quick context (≤400 tokens), links, `Now`, decisions log | Keep Quick context short and current; decisions are dated one-liners |
| `DESIGN.md` | Design rules with status: Confirmed / Used / Proposal / Deprecated | Only durable rules; a new decision you made is `Proposal` until Max approves |
| `REFERENCES.md` | Every source: client material, Figma frame, link, image | ID (`M1…` client materials, `R1…` references), what, where, status (approved / working / old / reference / unknown), use for. Other files cite these IDs |

Never invent client facts; mark guesses as guesses. Found along the way but not asked → `Now` → `Found (waiting for Max)`, do not do it.

## Folders

- `inbox/` — drop zone for anything new (briefs, PDFs, texts, logos, screenshots, link lists). On "process inbox": read each file once, put facts into `PROJECT.md`, rules into `DESIGN.md`, sources into `REFERENCES.md`, then move the file to `materials/` (from the client) or `refs/` (references, inspiration). Look at every image. A file of unclear origin goes to `refs/` with status `unknown` plus a question in `Found`; do not use it. Report what went where in 3–6 lines.
- `materials/` — client files, kept as originals. `refs/` — reference images and screenshots. Links live only in `REFERENCES.md`.
- `out/` — create only when a task produces files (HTML concept, exports, generated images). Figma work stays in Figma.

## Tasks

| Task | How |
| --- | --- |
| Sections or pages in Figma | Read and follow `.claude/skills/figma-sections/SKILL.md` |
| Edit a page of an existing project | Code path from `PROJECT.md` → Links. That repo's own rules win. Smallest change, one browser check (`chrome_devtools`), local checkpoint commit first if it has Git; never push unasked |
| Quick HTML concept | One self-contained file in `out/`, skill `frontend-design` (keep its planning internal). Placeholder art (simple SVG or blocks) is fine; generate images only if asked. Copy you invent is marked as such in the report |
| Improve an existing design or page | `impeccable` |
| Copy | Page copy `copywriting`; UI microcopy `better-writing` |
| Design system from approved screens | Build it in Figma (not code): follow `figma-sections` → "Design system"; `project-design-workflow` only to sort sources first |
| Inspiration | Max's library first (`find-cool-sites-references`), then One Page Love / A1 if needed; never copy literally |

Use global skills by name only at the step that needs them. Images: user's global image rules (fal).

## Checks

One check, then stop: desktop 1280 px, plus one phone width only if the layout changes there. Tool: `chrome_devtools`; if it fails, the agent's built-in browser. Open single HTML files directly (file URL), no preview server. Say what stayed unverified.

## Token rules

Batch independent reads. Search before opening; read fragments, not whole files. Do not reread unchanged files, repeat near-identical screenshots or re-check after a passing check. No polling. Ask only when the answer changes the result.

## Global lessons

If something learned here should apply to all projects (a rule, a skill change), do not edit global files on your own: propose it to Max in one line. On his OK, Claude edits `~/.claude/CLAUDE.md` and syncs `max-agent-skills`; Codex edits its global `AGENTS.md`.

# Light project

Small design and web tasks: Figma sections, fixes, one page of an existing project, quick HTML concepts. Works in Claude Code (via `CLAUDE.md`) and Codex (reads this file). Chat with Max in Russian; files in English unless the content itself is Russian.

## Every new chat

1. Read `PROJECT.md` (Quick context and Now; the whole file is fine while it is short). Open `DESIGN.md`, `REFERENCES.md` or `materials/` only when Quick context is not enough for the task.
2. One result = one chat. When a result is accepted, update memory (below) and suggest a new chat for the next task.
3. If `inbox/` has files, say so in one line and offer to process them; do not process unasked.

## Modes

- **Micro (default):** one result, one main skill, one sufficient check, no research, no sub-agents. Read the minimum; stop after the check passes.
- **Start of a new site or a big new part:** unless the materials already answer it, ask up to 5 short questions first (goal, audience, what must not change, done when), then write memory. Not for Micro tasks.
- **Standard:** several steps or several screens. Write 1–3 "done when" lines, what must not change, and a short checklist in `PROJECT.md` → `Now`; tick items as they are done.
- **Too big:** a full multi-page live site, logins, payments or a CMS → recommend moving to the big pack (`site-starter`) and stop.

## Memory (update in the same reply, only when something durable appeared; a result still under review changes nothing until Max accepts it: before «принято» touch only `Found` and open questions, never ticks, decisions or rules)

| File | Holds | Rule |
| --- | --- | --- |
| `PROJECT.md` | Quick context (≤400 tokens), links, `Now`, decisions log | Keep Quick context short and current; decisions are dated one-liners with why and what breaks if reverted |
| `DESIGN.md` | Design rules and the Figma page kit, with status: Confirmed / Used / Proposal / Deprecated | Current state only, under ~2k tokens: replace outdated lines, never append a history. Only durable rules; a new decision you made is `Proposal` until Max approves |
| `REFERENCES.md` | Every source: client material, Figma frame, link, image | ID (`M1…` client materials, `R1…` references), what, where, status (approved / working / old / reference / unknown), use for. Other files cite these IDs |

Max's short commands: «принято» / «ок, утверждаю» = the result is accepted → update memory and suggest a new chat; «запомни: …» = write it to the right file and confirm in one line; «забудь / устарело: …» = mark it Deprecated or remove it.

Memory looks outdated → fix it now and say so in the report. Never invent client facts; mark guesses as guesses. Found along the way but not asked → `Now` → `Found (waiting for Max)`, do not do it.

## Folders

- `inbox/` — drop zone for anything new (briefs, PDFs, texts, logos, screenshots, link lists). On "process inbox" read `.claude/process-inbox.md` and follow it; do not process unasked.
- `materials/` — client files, kept as originals. `refs/` — reference images and screenshots. Links live only in `REFERENCES.md`.
- `out/` — create only when a task produces files (HTML concept, exports, generated images). Figma work stays in Figma.

## Tasks

| Task | How |
| --- | --- |
| Sections or pages in Figma | Read and follow `.claude/skills/figma-sections/SKILL.md` (it runs the global `figma-page-from-system`: kit scan, block plan with Max's OK, copies, scripted checks) |
| Edit a page of an existing project | Code path from `PROJECT.md` → Links. That repo's own rules win. Smallest change, one browser check (`chrome_devtools`), local checkpoint commit first if it has Git; never push unasked |
| Quick HTML concept | One self-contained file in `out/`, skill `frontend-design` (keep its planning internal). Placeholder art (simple SVG or blocks) is fine; generate images only if asked. Copy you invent is marked as such in the report |
| Design system from approved screens | Build it in Figma (not code): follow `figma-sections` → "Design system"; `project-design-workflow` only to sort sources first |

Global skills by name only at the step that needs them (copy `copywriting`/`better-writing`, redesign `impeccable`, inspiration Max's library first). Images: global fal rules.

## Checks

One check, then stop: desktop 1280 px, plus one phone width only if the layout changes there. Tool: `chrome_devtools`; if it fails, the agent's built-in browser. Open single HTML files directly (file URL), no preview server. Say what stayed unverified.

## Global lessons

A lesson for all projects: propose it to Max in one line; never edit global files on your own.

## Coded sites only

- Retrospective only when Max asks: review only this project's own session logs (via a chat-to-md export; never read or quote client data or secrets) for checks that found nothing, tokens spent re-reading context, and set-up that came late; write the result under `Found (waiting for Max)`.
- Applies to coded sites (HTML concept, a page of an existing project), not Figma-only projects: after the first finished page, ask Max once whether to set up a free preview deploy for a real-phone check. Setup, any push and each later redeploy need his separate yes. Treat the link as public: noindex, no unreleased client material or secrets.

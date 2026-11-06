---
name: figma-sections
description: Draw or edit website sections and pages in Figma for a light-starter project through the figma-console MCP, from the file's own styles and components, following the global skill figma-page-from-system. Use for "сделай секции в Figma", "нарисуй страницу", "вторичка по главной", "поправь блок в макете".
---

# Figma sections (light-starter)

The method lives in the global skill `figma-page-from-system` (`~/.claude/skills/figma-page-from-system/SKILL.md`; Codex: its own copy of that skill). Read it and follow it. This file only adds what is specific to a light-starter project.

## Project specifics

- **Connect once per chat:** `figma_get_status` with `probe: true`. Not connected → ask Max to open the file in Figma Desktop and run Plugins → Development → **Figma Desktop Bridge**, then stop. Check the file name matches `PROJECT.md` → Links. Several files connected → pass `fileKey` on every call.
- **Page kit = `DESIGN.md`.** Write it from the global skill's `references/page-kit-template.md`; keep the Status mark (Confirmed / Used / Proposal) on rules that came from you rather than from the scan or Max.
- **Approved frames** are the ones with status `approved` in `REFERENCES.md`. The kit scan runs on all of them.
- **Placement:** new work goes into a named Section on the target page, beside or below existing content, never overlapping approved frames.
- **Copy:** real copy from `PROJECT.md` / `materials/`; if missing, short placeholders marked `[TBD]`.
- **Micro task** (one fix in an existing block): skip the kit and the plan stop; copy-diff or audit only the changed node, one screenshot.

## Design system (when asked to create or extend one)

Source = approved frames only. On a page named **Design system**: color variables by role (text on light, text on dark, surface, border, states) with a description each and scopes (text colors → text fills only, surfaces → frame fills); hide primitives from publishing; spacing variables; one text style per role; components only for repeated elements the approved frames show. Turn each `practice` line from the kit scan into a style only after Max says so. Record rules in `DESIGN.md`.

## Finish

Report in Russian, 3–6 lines: what was made (Section name, node link), what was cloned, check markers, open questions. Update `DESIGN.md` only for durable rules (after «принято»), `PROJECT.md` → `Now`.

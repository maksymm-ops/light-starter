---
name: figma-sections
description: Draw or edit website sections and pages in Figma for a light-starter project through the figma-console MCP, reusing the file's own styles and components and checking the result with one screenshot per pass. Use for "сделай секции в Figma", "нарисуй страницу", "поправь блок в макете".
---

# Figma sections

Tools: `figma-console` MCP. If it does not answer, `figma-bridge`; the official Figma MCP only as a last resort (Max is on the free Figma plan: a handful of calls per month). Say which one you used. Read-only tasks without Figma Desktop: figma-console reads by file URL (`fileUrl`) through the REST API.

## 1. Connect (once per chat)

`figma_get_status` with `probe: true`. Not connected → ask Max to open the file in Figma Desktop and run Plugins → Development → **Figma Desktop Bridge**, then stop. Check the connected file name matches `PROJECT.md` → Links.

## 2. Learn the file, cheapest first

- Design system: `figma_get_design_system_kit` with `format: "compact"` (tokens, styles, component names). Read `DESIGN.md` rows for the touched areas.
- Target page: `figma_get_file_data` `verbosity: "summary"`, `depth: 1`; only then the nodes you need.
- Look before building: `figma_capture_screenshot` of the target area (scale 1).
Never pull the full tree or full-format kits.

## 3. Build

- Do not modify approved frames unless Max asked. New work goes into a named **Section** on the target page, placed beside or below existing content, never overlapping.
- Reuse what exists: instances of the file's components (`figma_search_components` → `figma_instantiate_component`), its text styles and color variables. Create a new component or style only if nothing fits; mark it `Proposal` in `DESIGN.md`.
- One text style per heading level across the file: if two H2s differ, use the existing style (or ask), never add a one-off size.
- Auto layout on every frame; "fill container" for content that should stretch; sizes on the file's spacing scale (8px if none).
- Real copy from `PROJECT.md` / `materials/`; if missing, short realistic placeholders marked `[TBD]`.
- Desktop first; a mobile frame only if asked or obviously needed.
- Use `figma_execute` for anything the dedicated tools do not cover; on a failed attempt, delete partial layers before retrying.

## Design system (when asked to create or extend one)

Source = approved frames only (`REFERENCES.md` status approved). On a page named **Design system**:
1. Variables: color (brand, text, surface, border, states) and spacing; reuse existing collections, no duplicates.
2. Text styles: one per role (H1–H4, body, small, label) per breakpoint the file uses.
3. Components with variants for repeated elements actually present in the approved frames (button, link, card, input, nav, footer…). Do not invent states the frames do not show; list them as `Proposal`.
4. Replace matching raw layers in the approved frames with instances only if Max asked.
Record each rule in `DESIGN.md` (Confirmed if taken from approved frames, Proposal otherwise). After that, new sections are built only from this page.

## 4. Check (bounded)

One `figma_capture_screenshot` of the new Section. Fix demonstrated problems (overlap, misalignment, clipped text, wrong style) in one pass and capture once more. Maximum three passes; then report what is left.

## 5. Finish

Report in Russian, 3–6 lines: what was made (page / Section name, node link), which components and styles were reused, what is new (`Proposal`), open questions. Update `DESIGN.md` only for durable rules and `PROJECT.md` → `Now`.

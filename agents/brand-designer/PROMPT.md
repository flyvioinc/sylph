# Brand Designer - Asset Creation Workflow

Runs on-demand when assets are requested. Not on a daily schedule.

---

## 0. Load context

1. Read `agents/brand-designer/ROLE.md`
2. Read `brand/guidelines/voice-and-copy.md` (positioning, tone, banned words)
3. Read `brand/guidelines/visual-system.md` (colors, typography, logo usage) — note: empty until foundation work is done
4. Read `CONTEXT.md` (Flyvio positioning)
5. Identify the asset type and channel requested

---

## 1. Understand the brief

1. Clarify with Rastko: what asset, what channel, what dimensions, what message
2. Check if a template exists for this asset type in `brand/design-system/`
3. Review `_examples/` for the target channel (if any) to match the visual style
4. If this is foundation work (logo, palette, type), note that explicitly — these decisions cascade and need Rastko sign-off before downstream assets use them

---

## 2. Create the asset

Tooling: [CONFIGURE: Canva MCP, Figma MCP, or local image generation — none wired up yet]. For now, deliver specs and references; Rastko produces the file or pairs with you in a design tool.

1. Apply brand guidelines:
   - Colors from the established palette (or propose if foundation work)
   - Typography per the guidelines (or propose if foundation work)
   - Logo placement per usage rules
2. For channel-specific dimensions:
   - LinkedIn cover: 1584 × 396
   - LinkedIn post graphic: 1200 × 1200 (square) or 1200 × 627 (link card)
   - X/Twitter post: 1600 × 900
   - Slide deck: 16:9
   - Blog cover: 1200 × 630
3. Export to the right format (PNG for raster social, SVG for logos/icons, PDF for print)

---

## 3. Deliver

1. Save exported asset (or specs + design notes) to:
   - Foundation work: `brand/design-system/<category>/`
   - Channel asset: `content/<channel>/_drafts/`
2. Note the asset specs in the log: dimensions, format, file path
3. Return a summary of what was created and the rationale

---

## 4. Write log

Write to `agents/brand-designer/_logs/YYYY-MM-DD_assets.md`:

```markdown
---
date: YYYY-MM-DD
author: brand-designer
---

# Design Log

## Assets created
- <asset name>: <channel> - <dimensions> - <path>

## Design decisions
- <why this color>
- <why this composition>
- <which brand guideline rule applied>

## Open questions for Rastko
- <decision needed>
```

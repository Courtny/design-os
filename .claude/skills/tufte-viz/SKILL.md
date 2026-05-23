---
name: tufte-viz
description: |
  Ideate and critique data visualizations using Edward Tufte's principles. Use when designing charts, improving dashboards, checking graphical integrity, reducing chartjunk, or planning small multiples and high-density displays.
version: 1.0
user-invocable: true
---

# `/tufte-viz` - Tufte Data Visualization Review

Apply Edward Tufte's principles to design clear, honest, high-density data visualizations. For general layout and UI critique, use `/visual-critique` instead.

## Quick Start

```
/tufte-viz                                    → Guided questions, then describe or attach the viz
/tufte-viz [attach image]                     → Critique a chart, dashboard, or report screenshot
/tufte-viz [paste spec or describe dashboard] → Review viz decisions in a spec or flow
```

**Output:** Review saved to `outputs/critique-notes/[feature]-tufte-viz-[date].md`
**Time:** 10–20 minutes depending on scope
**Dependencies:** None. Works from images, specs, or descriptions. Figma MCP helps if connected.

---

## Context Routing (Internal)

Before ideating or critiquing, check:

| Source | Files/Folders | What to extract |
|--------|---------------|-----------------|
| Tufte reference | `context-library/foundations/tufte-principles.md` | Lie factor, data-ink ratio, chartjunk, small multiples, Tufte test |
| Semantic color | `context-library/foundations/semantic-color.md` | Color encoding vs decoration in charts |
| WCAG | `context-library/foundations/wcag.md` | Contrast, alt text for charts, color independence |
| Design principles | `context-library/design-system/principles.md` | Team rules that may constrain chart treatment |
| Storybook | `context-library/design-system/storybook.md` | Existing chart components if documented |
| Brief or spec | `outputs/briefs/` or described in chat | What insight the viz must support |

Read `context-library/foundations/tufte-principles.md` for the full reference before applying the frameworks below.

---

## Guided Questions

Ask these if the designer hasn't given context:

1. "What am I looking at? (Single chart, dashboard, report page, in-product analytics)"
2. "What's the one comparison or insight this needs to support?"
3. "Who's the audience? (Exec summary, analyst, end user in workflow)"
4. "Is this new design or a critique of something existing?"
5. "Any chart library or component constraints? (e.g., Recharts, design system chart tokens)"

---

## Workflow: New Visualizations

### 1. Clarify the data story

- What comparisons matter?
- What's the key insight to communicate?
- Who's the audience?

### 2. Select approach (Tufte-aligned)

- High comparison need → Small multiples
- Dense data → Data tables, sparklines, condensed time-series
- Time-series → Line charts with minimal grid
- Part-to-whole → Prefer bar or table over pie chart

### 3. Design with data-ink in mind

- Start minimal; add only what's necessary
- Every element must earn its ink
- Default to grayscale; use color purposefully (check `semantic-color.md`)

### 4. Apply the Tufte test

Run all seven checks from `tufte-principles.md` Quick Reference before handoff.

---

## Workflow: Critiquing Visualizations

Work through each area. Only include findings where there's something worth saying.

### 1. Graphical integrity

- Does visual effect match data effect? (Lie Factor ≈ 1.0; flag if > 1.05 or < 0.95)
- Are baselines and scales honest? (No truncated axes that exaggerate change)
- Any 3D distortion on 2D data?
- Is context provided? (Sources, units, time range, definitions)
- Are intervals consistent?

### 2. Chartjunk

- Decorative elements, heavy grids, gradients, shadows without purpose
- Moiré patterns, busy cross-hatching
- "Duck" graphics where design competes with data
- Clip art or icons that don't encode data

### 3. Data-ink ratio

- Apply the eraser test: what can be removed without losing information?
- Redundant labels, borders, boxes, excessive tick marks
- 3D when 2D suffices

### 4. Excellence, comparison, and density

- Can viewers compare data elements easily?
- Multiple levels of detail (overview + fine structure)?
- Could more data fit in the same space without hurting readability?
- Would small multiples serve comparison better than one busy chart?

### 5. Color and accessibility

- Color used for encoding, not decoration (cross-check `semantic-color.md`)
- Colorblind-safe palettes; gray default, color for emphasis
- Not relying on color alone for meaning (cross-check `wcag.md`)

### 6. Suggest improvements

For each issue: specific before/after recommendation tied to a Tufte principle.

---

## Quick Checklist

- [ ] Lie Factor ≈ 1.0 (no visual distortion)
- [ ] Maximum data-ink ratio
- [ ] Zero chartjunk
- [ ] Clear labeling (units, sources, scales)
- [ ] Enables comparison
- [ ] Reveals multiple levels of detail
- [ ] Appropriate data density

---

## Output Structure

```markdown
# Tufte Viz Review: [Chart, Dashboard, or Feature Name]

**Date:** [date]
**Source:** [image / spec / Figma link / description]
**Mode:** [new design / critique]

---

## Summary

[2–3 sentences: overall viz health. Is the data honest, clear, and dense, or buried in decoration?]

---

## Data Story

[What comparison or insight this viz supports, and whether the design serves it.]

---

## Tufte Test Results

| # | Check | Pass / Flag | Notes |
|---|-------|-------------|-------|
| 1 | Data-ink | | |
| 2 | Integrity (Lie Factor) | | |
| 3 | Chartjunk | | |
| 4 | Excellence (multi-level) | | |
| 5 | Comparison | | |
| 6 | Density | | |
| 7 | Context | | |

---

## Findings

| # | Issue | Location | Principle | Recommendation |
|---|-------|----------|-----------|----------------|
| 1 | [what's wrong] | [where] | [e.g., chartjunk, integrity] | [specific fix] |

---

## What's Working Well

[Specific decisions to preserve.]

---

## Suggested Next Steps

[1–3 actions. e.g., "Remove heavy grid," "Try small multiples for segment comparison," "Run /color-review on chart palette."]
```

---

## Quality Check Before Saving

- [ ] `foundations/tufte-principles.md` read and referenced
- [ ] Tufte test (all 7 checks) completed
- [ ] Integrity and lie factor considered for proportional encodings
- [ ] Chartjunk and data-ink pass done
- [ ] Color checked against `semantic-color.md` where color is used
- [ ] Accessibility flagged via `wcag.md` where relevant
- [ ] Recommendations are specific (before/after), not generic "simplify"
- [ ] Scope stayed on data viz (did not duplicate full `/visual-critique`)

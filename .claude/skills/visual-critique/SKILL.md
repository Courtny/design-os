---
name: visual-critique
description: Critique a design from an attached image — component, page layout, or mobile screen. Grounded in your design system principles and component UX guidance.
version: 1.0
user-invocable: true
---

# `/visual-critique` - Visual Design Critique

Review a design artifact from an attached image. Works with screenshots, exports, Figma screen captures, or photos of sketches. No MCP required.

## Quick Start

```
/visual-critique                               → Attach an image and I'll ask a few questions
/visual-critique [attach image]                → I'll run the critique with clarifying questions
/visual-critique [attach image] [context]      → Best path: image + what you're reviewing and what decisions you need
```

**Output:** Critique saved to `outputs/critique-notes/[feature]-visual-critique-[date].md`
**Time:** 10–15 minutes
**Dependencies:** None — works fully offline from local context files

---

## Context Routing (Internal)

Before reviewing the image, check:

| Source | Files/Folders | What to extract |
|--------|---------------|-----------------|
| Principles | `context-library/design-system/principles.md` | Core UX principles and anti-patterns to check against |
| Component UX | `context-library/design-system/component-ux/` | Rules, states, and common mistakes for components visible in the image |
| Research | `context-library/research/` | Known user expectations or pain points relevant to what's shown |
| Past critique notes | `context-library/meetings/` | Recurring feedback patterns to watch for |
| Brief or spec | `outputs/briefs/` or described in chat | What problem this design is solving and what decisions are open |

---

## Guided Questions

Ask these when no context is provided alongside the image:

1. "What is this? (Component, page layout, mobile screen, flow step)"
2. "What stage is this? (Early sketch, lo-fi, hi-fi, near-final)"
3. "What specific decisions do you need feedback on?"
4. "What's already decided and shouldn't be up for debate?"
5. "What platform is this for? (Web, iOS, Android)"

Skip questions the image makes obvious.

---

## Critique Framework

Work through each area below. Only include findings where there's something worth saying. Don't manufacture issues.

### 1. Visual Hierarchy

- Is there a clear primary action or focal point?
- Do the most important elements command the most visual weight?
- Does anything compete with the primary CTA for attention?
- Is the reading order (top-to-bottom, left-to-right for LTR) logical?

### 2. Spacing and Grid

- Is spacing consistent? Does it look like it follows a defined scale?
- Are related elements grouped tightly? Are unrelated elements separated clearly?
- Flag anything that looks arbitrarily spaced or misaligned.
- Note if spacing on mobile looks tight for touch targets (min 44x44px).

### 3. Component Identification and Usage

- Identify any components visible that match patterns in `context-library/design-system/component-ux/`.
- For each matched component: does its usage align with the team's guidance? Flag specific violations.
- Note any patterns that appear to be custom-drawn when a standard component likely exists.
- If `storybook.md` is filled out, note whether visible components are likely in the library.

### 4. Typography

- Is type scale consistent? Does hierarchy feel clear through type size and weight?
- Are there any readability concerns (line length, line height, small text)?
- Check capitalization: does it match the team's convention (typically sentence case)?
- Flag any text that looks like it might not meet contrast thresholds (4.5:1 for normal text).

### 5. Color and Contrast

- Do colors appear to follow the team's palette (check `principles.md` for defined colors)?
- Flag any text-on-background combinations that look low contrast.
- Is color used as the only differentiator for state (error, warning, success)? If so, flag it.
- Are semantic colors (error = red, success = green) used for their semantic meaning only?

### 6. Microcopy

- Are labels, CTAs, and headings specific and action-oriented?
- Do button labels tell users what happens (verb + object: "Save changes," not "Submit")?
- Is the tone consistent with the team's voice (check `writing-style-*.md` if filled)?
- Flag any placeholder copy, TBD content, or lorem ipsum still visible.

### 7. State Coverage

- What states are shown? (Default, hover, active, disabled, loading, error, empty)
- What states appear to be missing from the design shown?
- Are error states shown? Do they tell users what went wrong and how to fix it?
- Is there an empty state accounted for?

### 8. Accessibility (Visual Observations)

- Do any interactive elements look too small for touch or click targets?
- Are focus states visible (in hi-fi designs)?
- Does the design rely on color alone to communicate status?
- Is there sufficient visual separation between interactive and non-interactive elements?
- Does anything look like it could cause problems for screen readers (unlabeled icon buttons, missing context)?

### 9. Responsive Considerations

- If this is a web layout: how would this adapt to a narrower viewport?
- Are there any patterns that would break at mobile sizes?
- Is anything stacked or arranged in a way that assumes a fixed width?

---

## Output Structure

```markdown
# Visual Critique: [Screen or Feature Name]

**Date:** [date]
**Stage:** [sketch / lo-fi / hi-fi / near-final]
**Platform:** [web / iOS / Android / all]
**Source:** [description of image or "image attached in chat"]

---

## Summary

[2–3 sentences on overall quality and the most important opportunities. Be specific.]

---

## Findings

| # | Location | Observation | Recommendation | Ties to |
|---|----------|-------------|----------------|---------|
| 1 | [element or area] | [what's happening] | [specific fix] | [principle or component-ux rule, if applicable] |

---

## What's Working Well

[Specific things to preserve — not just "good job." Name them so they don't get accidentally changed.]

---

## Missing States or Gaps

[States, edge cases, or flows that aren't visible in the image but need to be accounted for.]

---

## Open Questions

[Things that can't be resolved from the image alone. These should become agenda items or decision logs.]

---

## Suggested Next Steps

[1–3 concrete actions. Link to relevant skill if applicable, e.g., "Run `/accessibility-review` on the form section."]
```

---

## Severity Framing for Findings

Don't label every finding — just lead with the most important ones. When you do flag severity:

| Signal | Meaning |
|--------|---------|
| Critical | Blocks a user or violates a core principle. Fix before moving forward. |
| Serious | Real friction. Should be resolved before handoff. |
| Minor | Polish or consistency. Backlog-worthy. |

---

## Quality Check Before Saving

- [ ] Principles and component-ux files checked before writing findings
- [ ] Findings reference specific locations in the design, not just generic advice
- [ ] At least one "what's working" item (if anything is)
- [ ] Missing states section is complete — don't skip it
- [ ] Open questions are written as questions, not findings
- [ ] Output matches the team's voice: direct, specific, not generic

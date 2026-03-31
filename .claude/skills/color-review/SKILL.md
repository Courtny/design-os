---
name: color-review
description: Review color usage in a design for semantic consistency, token adherence, and accessibility. Works from attached images, specs, or Figma files.
version: 1.0
user-invocable: true
---

# `/color-review` - Semantic Color Review

Evaluate how color is used in a design. Not just "is it the right shade of blue," but "does every color mean something, and does that meaning hold up everywhere?"

## Quick Start

```
/color-review                                → Guided questions, then attach or describe the design
/color-review [attach image]                 → Analyze color usage from a screenshot or export
/color-review [paste spec or describe flow]  → Review color decisions in a spec
```

**Output:** Review saved to `outputs/critique-notes/[feature]-color-review-[date].md`
**Time:** 10–15 minutes
**Dependencies:** None. Works from images, specs, or descriptions. Figma MCP helps if connected.

---

## Context Routing (Internal)

Before reviewing, check:

| Source | Files/Folders | What to extract |
|--------|---------------|-----------------|
| Color tokens | `context-library/design-system/principles.md` → Color section | Primary, secondary, semantic colors, and any color rules |
| Foundations | `context-library/foundations/semantic-color.md` | The principle of semantic color and common anti-patterns |
| Component UX | `context-library/design-system/component-ux/` | Color rules tied to specific components (e.g., destructive button uses error red) |
| Accessibility | `context-library/design-system/principles.md` → Accessibility section | Contrast ratios and color independence requirements |
| Storybook | `context-library/design-system/storybook.md` | Token naming conventions if documented |

---

## Guided Questions

Ask these if the designer hasn't given context:

1. "What am I looking at? (Component, page, flow, full screen)"
2. "Are you using design tokens, or working from raw hex values?"
3. "Is there a dark mode or alternate theme to consider?"
4. "Any colors you're unsure about or want a second opinion on?"

---

## What Semantic Color Means

Read `context-library/foundations/semantic-color.md` for the full reference. The short version:

**Semantic color** means every color in the UI communicates something specific and does so consistently. Red always means error or danger. Green always means success or confirmation. Blue always means interactive or informational. Colors aren't decorative by default; they carry meaning.

When a color is used without semantic intent (purely for aesthetics, branding flair, or visual variety), it creates noise. Users learn your color language fast, and inconsistency teaches them the wrong things.

---

## Review Framework

### 1. Color Inventory

List every distinct color visible in the design. For each:
- What role does it play? (Brand, semantic, decorative, interactive, neutral/structural)
- Is it a defined token from `principles.md`, or a one-off value?
- Does it appear in more than one place? If so, is the meaning consistent?

Flag any colors that don't map to the team's defined palette or token system.

### 2. Semantic Consistency

For each semantic color used (success, warning, error, info):
- Is it used only for its semantic purpose?
- Is the same semantic meaning always represented by the same color?
- Are there places where a semantic color is used decoratively? (e.g., green used as a brand accent when it also means "success" elsewhere)

**Common violations:**
- Red used for both errors and "hot/trending" indicators
- Green used for both success states and brand accent
- Blue used for both links and info banners (sometimes fine, but worth checking)
- Yellow/amber used for both warnings and highlights/emphasis

### 3. Color Independence

Does the design rely on color alone to communicate state or meaning?

Check for:
- Error states indicated only by red (no icon, no text, no border change)
- Status badges differentiated only by color (no label, no icon)
- Required fields marked only with a colored asterisk
- Active/selected states indicated only by color change

For every instance: what secondary indicator exists? If none, flag it.

### 4. Contrast and Legibility

- Text on colored backgrounds: does it meet 4.5:1 for normal text, 3:1 for large text?
- UI components (icons, borders, focus rings) on their backgrounds: 3:1 minimum?
- Any text on images or gradients where contrast varies?
- Light text on light backgrounds or dark text on dark backgrounds?

Don't try to calculate exact ratios from screenshots. Flag anything that looks like it might fail, and recommend the designer verify with a contrast checker.

### 5. Token Adherence

If the team's `principles.md` defines a color system:
- Are all colors in the design traceable to a defined token?
- Are any raw hex values being used instead of tokens?
- Are any token values being used for the wrong purpose (e.g., using the error token for a decorative border)?

If `principles.md` color section isn't filled out yet, note this as a gap and suggest the designer define their tokens.

### 6. Dark Mode and Theme Readiness

If the product supports or will support dark mode:
- Are colors defined as semantic roles (success, error) rather than absolute values (#FF0000)?
- Would the current color choices invert well, or are there hardcoded values that would break?
- Are any colors chosen specifically for a light background that wouldn't work on dark?

If dark mode isn't a consideration, skip this section.

### 7. Brand vs. Semantic Tension

This is the most common problem. The brand's primary color often collides with a semantic color:
- Brand blue and "interactive/link" blue are the same. Fine in most cases, but flag if the brand blue appears on non-interactive elements.
- Brand green and "success" green are the same. Problematic if green appears decoratively.
- Brand red and "error" red overlap. Rarely a good idea.

Note any collisions and suggest how to resolve them (typically by shifting the brand use slightly or adding a secondary differentiator).

---

## Output Structure

```markdown
# Color Review: [Screen or Feature Name]

**Date:** [date]
**Source:** [image / spec / Figma link / description]
**Token system defined:** [yes / partial / no — based on principles.md]

---

## Summary

[2–3 sentences: overall color health. Is the color system working semantically, or is it decorative?]

---

## Color Inventory

| Color | Role | Token match | Used consistently | Notes |
|-------|------|-------------|-------------------|-------|
| [hex or description] | [semantic / brand / decorative / interactive / neutral] | [yes / no / N/A] | [yes / no] | |

---

## Findings

| # | Issue | Location | Recommendation | Ties to |
|---|-------|----------|----------------|---------|
| 1 | [what's happening] | [where] | [specific fix] | [principle, token, or WCAG criterion] |

---

## Color Independence Check

[List every place color is the only differentiator. For each, note whether a secondary indicator exists.]

---

## What's Working Well

[Specific color decisions to preserve.]

---

## Gaps

[Missing token definitions, undocumented colors, dark mode considerations.]

---

## Suggested Next Steps

[1–3 actions. e.g., "Define your semantic color tokens in principles.md," "Run /accessibility-review for full contrast audit."]
```

---

## Quality Check Before Saving

- [ ] `principles.md` Color section checked (or flagged as empty)
- [ ] `foundations/semantic-color.md` referenced for grounding
- [ ] Every distinct color in the design inventoried
- [ ] Color independence check completed (WCAG 1.4.1)
- [ ] Contrast flagged where it looks suspect (not calculated, just flagged)
- [ ] Semantic consistency evaluated: same meaning, same color, everywhere
- [ ] Brand vs. semantic tensions called out explicitly
- [ ] Token adherence checked (or token gap flagged)

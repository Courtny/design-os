---
name: prototype
description: Generate an HTML/CSS/JS or React prototype using the team's design system components and tokens. Use when the designer wants to quickly explore a layout, interaction pattern, or component state before writing a spec or taking it into Figma. Use for visual explorations, dev reference artifacts, and stakeholder previews.
version: 1.0
user-invocable: true
---

# `/prototype` — Quick Prototype Generator

Turn a layout idea, component state, or interaction pattern into a working prototype grounded in the real design system.

## Quick Start

```
/prototype                                   → Guided questions, then generate
/prototype [describe what you want to build] → Skip the questions
/prototype [paste a spec or brief]           → I'll extract what to prototype from it
```

**Output:** Saved to `outputs/prototypes/[feature-name]-prototype.html` (or `.tsx`)
**Time:** 5–15 minutes

---

## Context Routing (Internal)

Before generating, check:

| Source | File | What to extract |
|--------|------|-----------------|
| Component library | `context-library/design-system/storybook.md` | Which components exist, exact names, key props |
| Component UX guidance | `context-library/design-system/component-ux/` | Do/avoid rules, states, accessibility notes |
| Design principles | `context-library/design-system/principles.md` | Visual language tokens, accessibility standards, anti-patterns |
| Brief or spec | `outputs/briefs/` or `outputs/design-specs/` | Scope, states, edge cases to include |
| Figma MCP (if connected) | Design file | Current visual state to match or diverge from |

---

## Guided Questions

Ask only what you don't already know. Start with 1–2, not all at once.

1. "What are you prototyping? (single component, page section, full flow?)"
2. "Platform: web desktop, mobile web, or both?"
3. "Which Storybook components do you expect to be involved?"
4. "What's this for? (personal exploration, stakeholder review, dev reference?)"
5. "Should I show a specific state? (error, empty, loading, success?)"

---

## Generation Rules

### Use the design system first

- Check `context-library/design-system/storybook.md` before proposing any component. If it exists in Storybook, use it.
- Match component names exactly as they appear in Storybook (PascalCase: `Button`, `FormField`, `DataTable`)
- Match variant names exactly: `Button (primary)`, `Button (ghost)`, `Alert (error)`
- Reference props by their camelCase names: `isDisabled`, `helperText`, `isLoading`
- Use design tokens for color, spacing, and type — never hardcode hex values or arbitrary pixel values

### Flag new patterns explicitly

When you had to invent a pattern not covered by Storybook, call it out at the top of the output file:

```
⚠️ New pattern: [PatternName] — not in Storybook.
Needs design system review before shipping.
Used in: [describe where in the prototype]
```

### Accessibility baseline (non-negotiable)

Every prototype must meet these minimums from `principles.md`:

- Semantic HTML: `<button>` for actions, `<a>` for navigation, `<label>` associated with every input
- Color contrast: 4.5:1 for body text, 3:1 for large text and UI components
- Focus states visible on all interactive elements (never `outline: none` without a custom replacement)
- Focus order matches visual reading order
- `aria-label` on any icon-only button or control with no visible text label
- Images have meaningful `alt` text (or `alt=""` if decorative)
- `prefers-reduced-motion` respected: wrap animations in the media query

### Responsive default

- Default to mobile-first unless the designer specifies desktop-only
- Prototype should render reasonably at 375px (mobile) and 1280px (desktop)
- Note any breakpoint behavior that differs significantly between sizes

### States to consider

Don't prototype only the happy path. For any interactive element, ask whether these states are in scope:
- Default, hover, focus, active, disabled
- Loading (use `Spinner` or `ProgressBar` from Storybook)
- Error (use `Alert (error)` or `FormField` with `isInvalid`)
- Empty (use `EmptyState` from Storybook — always include a next action)
- Success

If a state is out of scope for this prototype, note it explicitly.

---

## Output Format

At the top of every output file, include a header block:

```
<!--
  Prototype: [Feature or component name]
  Date: [YYYY-MM-DD]
  For: [exploration / stakeholder review / dev reference]
  Platform: [web / mobile / both]

  Storybook components used:
  - [Component name] — [Storybook path]
  - [Component name] — [Storybook path]

  New patterns (not in Storybook):
  - [PatternName] — needs design system review
  (or "None")

  States shown:
  - [list states]

  States out of scope:
  - [list anything explicitly excluded]
-->
```

---

## Quality Checklist

Before saving:

- [ ] Header block present and complete
- [ ] All components named exactly as in Storybook
- [ ] Design tokens used — no hardcoded hex or arbitrary px values
- [ ] New patterns called out at top of file and flagged for DS review
- [ ] All interactive elements have visible focus states
- [ ] Color contrast meets 4.5:1 for body text, 3:1 for UI components
- [ ] Semantic HTML throughout (buttons are `<button>`, not `<div>`)
- [ ] `aria-label` on icon-only controls
- [ ] `prefers-reduced-motion` respected for any animation
- [ ] Renders at 375px and 1280px without breaking
- [ ] All in-scope states shown; out-of-scope states explicitly noted
- [ ] Saved to `outputs/prototypes/[feature-name]-prototype.html` (or `.tsx`)

---

## Output Quality Self-Check

After generating, scan for:
- Any hardcoded color value (e.g. `#3B82F6`) → replace with the design token
- Any component name that doesn't match Storybook exactly → correct it
- Any `div` doing the job of a `button` or `a` → fix the semantic element
- Any animation without a `prefers-reduced-motion` check → add it
- Any `outline: none` without a visible replacement → add a focus style

---

## Example Header Block

```html
<!--
  Prototype: Exception Log Filter Panel
  Date: 2026-03-31
  For: Dev reference
  Platform: Web (desktop)

  Storybook components used:
  - Button (primary, secondary) — Actions > Button
  - FormField — Forms > FormField
  - Select (multi, searchable) — Forms > Select
  - Badge (neutral, warning, error) — Data > Badge
  - Drawer (right) — Overlay > Drawer

  New patterns (not in Storybook):
  - FilterChipRow — horizontal scrolling chip list for active filters.
    Needs design system review before shipping.

  States shown:
  - Default (drawer closed)
  - Drawer open with no filters selected
  - Drawer open with 3 active filters
  - Results filtered (Badge counts updated)

  States out of scope:
  - Loading state (no async in this prototype)
  - Mobile layout
-->
```

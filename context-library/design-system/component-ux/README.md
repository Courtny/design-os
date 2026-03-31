# Component UX Guidance

This folder contains per-component UX rules: when to use a component, how to use it correctly, what to avoid, and accessibility requirements.

The copilot reads these files when drafting specs or reviewing design decisions. The richer these files are, the more specific and accurate the output.

---

## File Naming

One file per component or closely related component cluster:

```
button.md
form-field.md
data-table.md
modal.md
toast-alert.md
navigation.md
```

Component names here **must match** the Storybook component name exactly (PascalCase becomes lowercase-hyphenated in the filename: `DataTable` → `data-table.md`).

---

## File Format

Use `templates/component-ux-template.md` as the starting point for each new file.

Each file should cover:
- **When to use** (and when not to)
- **Do / Prefer** (2–5 specific rules)
- **Avoid** (explicit anti-patterns)
- **States** (which states exist and what triggers them)
- **Accessibility** (focus behavior, ARIA, keyboard)
- **Pairings** (what it works well with, what conflicts)
- **Links** to Storybook story path and Figma component

---

## Current Files

| File | Storybook Path | Category |
|------|---------------|----------|
| [`button.md`](button.md) | Actions > Button | Actions |
| [`form-field.md`](form-field.md) | Forms > FormField | Forms |
| [`modal.md`](modal.md) | Overlay > Modal | Overlay |
| [`data-table.md`](data-table.md) | Data > DataTable | Data Display |
| [`card.md`](card.md) | Layout > Card | Layout |
| [`alert.md`](alert.md) | Feedback > Alert | Feedback |
| [`empty-state.md`](empty-state.md) | Data > EmptyState | Data Display |

---

## Getting Started

Start with your 5–10 most-used components. Even a short file with 3 "do" bullets and a Storybook link is valuable. Grow it over time.

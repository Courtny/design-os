# FormField — Component UX Guidance

**Storybook:** `Forms > FormField`
**Figma:** _(add your Figma component link)_

---

## When to Use

Use `FormField` as the wrapper for any form input: text inputs, selects, checkboxes, radio groups. It provides the `<label>`, `helper-text`, and error message in a consistent, accessible structure.

**Always use `FormField` instead of placing raw inputs.** A bare `TextInput` without `FormField` loses the label association and the consistent error/helper text layout.

---

## Props

| Prop | Values | Notes |
|------|--------|-------|
| `label` | string | Always required. Visible label text. |
| `helperText` | string | Optional. Appears below the input. Use for format hints or important context. |
| `errorMessage` | string | When the field has an error. Replaces `helperText` visually. Always paired with `isInvalid`. |
| `isRequired` | boolean | Adds visual indicator and `required` attribute. |
| `isDisabled` | boolean | Disables the input. Label and helper text remain visible. |
| `isInvalid` | boolean | Triggers error styling on the wrapped input. |

---

## Do

- Always provide a visible `label`. Placeholder text is not a substitute for a label.
- Use `helperText` for constraints the user needs before they type: "Must be 8–20 characters" before they've made an error.
- Use `errorMessage` after validation fails. Be specific: "Password must be at least 8 characters" beats "Invalid password."
- Mark truly required fields with `isRequired`. Don't mark every field optional unless it genuinely is.
- Group related fields visually — whitespace and grouping reduce cognitive load.

---

## Avoid

- Avoid using placeholder text as the only label. Placeholder disappears on focus and fails accessibility.
- Avoid error messages that say what went wrong but not how to fix it: "Invalid input" is useless. "Email must include @" is helpful.
- Avoid disabling form submission without explaining why and which fields are invalid.

---

## States

| State | Notes |
|-------|-------|
| Default | Label + input + optional helper text |
| Focus | Input border highlight; label stays visible |
| Error | `isInvalid` + `errorMessage`. Error message replaces helper text below the input. Input border turns error color. |
| Disabled | Input greyed out. Label reduced opacity but still readable. |
| Read-only | Input not editable but value is visible. Use when showing data in an edit form that can't be changed. |

---

## Accessibility

- `FormField` automatically associates `<label>` with the input via `htmlFor` / `id`. Don't break this.
- `errorMessage` is rendered with `role="alert"` so screen readers announce it on validation.
- `helperText` is associated with the input via `aria-describedby`.
- `isRequired` adds both visual indicator and `aria-required="true"` to the input.
- Color alone is never the only indicator of error state — the `errorMessage` text is required.

---

## Pairings

- `FormField` + `TextInput` — standard text entry
- `FormField` + `Select` — dropdown selection
- `FormField` + `RadioGroup` — single choice from a small set
- `FormField` + `Checkbox` — single boolean or grouped multi-select

---

## Common Mistakes

- Wrapping with `FormField` but forgetting to pass `isInvalid` when showing an `errorMessage`. The error styling won't apply to the input.
- Using `helperText` after the fact (only shown on error) instead of before. Users benefit from format hints before they've made a mistake.
- Using a single `FormField` for a checkbox group instead of a `<fieldset>` + `<legend>` pattern. For groups, use `CheckboxGroup` or `RadioGroup` which handle grouping semantics.

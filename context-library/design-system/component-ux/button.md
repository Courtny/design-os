# Button — Component UX Guidance

**Storybook:** `Actions > Button`
**Figma:** _(add your Figma component link)_

---

## When to Use

Use `Button` for user-initiated actions: submitting a form, saving changes, triggering a flow, or confirming a dialog.

**Not for navigation.** If clicking takes the user to a different page or view without performing an action, use a link (`LinkButton` or a plain `<a>`) instead. Buttons are for actions; links are for destinations.

---

## Variants

| Variant | When to use |
|---------|-------------|
| `primary` | The single most important action on a page or in a section. One per view. |
| `secondary` | Supporting actions. Can appear alongside a primary button. |
| `ghost` | Low-emphasis actions in dense UIs or repeated in a list/table. |
| `destructive` | Irreversible actions only: delete, remove, revoke. Always confirm before executing. |
| `icon-only` | Toolbars or very tight spaces. Always include `aria-label`. |

---

## Do

- Use one `primary` button per logical section. Two "primary" buttons compete for attention and create confusion.
- Label buttons with a verb: "Save," "Delete account," "Add member." Not "OK," "Submit," or "Yes."
- Use sentence case: "Save changes," not "Save Changes."
- Disable the button when action is not available. Don't hide it — hiding removes the affordance.
- Pair a destructive action with a confirmation step before executing.

---

## Avoid

- Avoid vague labels: "OK," "Click here," "Continue." Tell users what happens.
- Avoid buttons that look like headings or vice versa. If it doesn't do something, it's not a button.
- Avoid stacking more than two buttons side by side on mobile. Stack them vertically instead.
- Avoid using the `ghost` variant as the primary call to action. It's too low contrast for the most important action.

---

## States

| State | Triggered by | Notes |
|-------|-------------|-------|
| Default | Initial render | |
| Hover | Mouse hover | Shows intent |
| Focus | Keyboard focus (Tab) | Must be visibly distinct from hover |
| Active | Mouse/touch press | Brief feedback |
| Disabled | `isDisabled` prop | Reduce opacity. Keep the button visible. |
| Loading | `isLoading` prop | Show spinner inside the button; disable click. Preserve button dimensions. |

---

## Accessibility

- All buttons are keyboard focusable and activatable with Enter or Space.
- `icon-only` buttons must have `aria-label` with a meaningful description of the action.
- Disabled buttons use `aria-disabled="true"` (not just `disabled`) when you still want them in the tab order so screen reader users know the action exists.
- Focus ring must meet 3:1 contrast ratio against the adjacent background.
- Loading state should announce to screen readers: add `aria-live="polite"` on the status region, not just visually change the button.

---

## Pairings

- `Button (primary)` + `Button (secondary)` — standard action pair in forms and dialogs
- `Button (destructive)` + `Modal (confirmation)` — always confirm destructive actions
- `IconButton` + `Tooltip` — always pair icon-only buttons with a tooltip for sighted users

---

## Common Mistakes

- Using `primary` for two actions on the same screen. Decide which is primary.
- Using loading state without preserving button width. The layout shift is jarring.
- Forgetting to disable a loading button — users double-submit.

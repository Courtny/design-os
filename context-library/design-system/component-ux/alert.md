# Alert — Component UX Guidance

**Storybook:** `Feedback > Alert`
**Figma:** _(add your Figma component link)_

---

## When to Use

Use `Alert` to communicate important information that requires the user's attention but doesn't block their workflow. Alerts are persistent, visible messages that sit within the page content.

Use `Alert` instead of `Modal` when the message doesn't require a decision before continuing.

---

## Variants

| Variant | When to use | Color meaning |
|---------|-------------|---------------|
| `info` | Neutral, helpful context. Tips, announcements, or general guidance. | Blue / info token |
| `success` | Confirming a completed action. Form submitted, settings saved. | Green / success token |
| `warning` | Something needs attention but isn't an error yet. Expiring subscription, unsaved changes. | Yellow / warning token |
| `error` | Something went wrong. Validation failure, server error, permission denied. | Red / error token |

---

## Do

- Use the variant that matches the semantic meaning. Don't use `error` for warnings or `info` for errors.
- Keep alert text concise. One to two sentences max. Lead with what happened, then what to do about it.
- Include a recovery action when possible. "Your session expired. [Sign in again]" is better than "Session expired."
- Place the alert near the content it relates to. A form validation summary goes above the form. A page-level message goes at the top of the page.
- Use `role="alert"` or `aria-live="polite"` for alerts that appear dynamically so screen readers announce them.

---

## Avoid

- Avoid using alerts for content that isn't actually urgent or important. If everything is an alert, nothing is.
- Avoid stacking more than two alerts at a time. If multiple alerts compete for attention, consolidate them.
- Avoid using alerts inside modals. The modal is already interrupting; an alert inside it adds noise.
- Avoid color as the only indicator of alert type. The icon and text must convey the meaning independently.

---

## States

| State | Trigger | Notes |
|-------|---------|-------|
| Visible | Condition triggers alert | Alert renders in position with icon, text, and optional action. |
| Dismissible | User clicks close button (if enabled) | Alert fades or collapses. Focus moves to next logical element. |
| Dynamic entry | Action triggers alert after page load | Use `aria-live="polite"` so screen readers announce it without interrupting. |

---

## Accessibility

- Use `role="alert"` for critical alerts (errors) that need to interrupt the screen reader immediately.
- Use `aria-live="polite"` for non-critical alerts (info, success) that should be announced at the next pause.
- Don't rely on color alone to convey the alert type. Each variant should have a distinct icon and clear text.
- If the alert is dismissible, the close button needs `aria-label="Dismiss alert"` or equivalent.
- Focus management: if an alert appears in response to a user action, consider moving focus to the alert so it's not missed.

---

## Pairings

- `Alert (error)` above a form — form-level validation summary
- `Alert (success)` at the top of a page — confirmation after completing an action
- `Alert (warning)` inline — cautionary context near relevant content
- `Toast` instead of `Alert` — for ephemeral confirmations that auto-dismiss (use `Toast` for "saved" messages that don't need to persist)

---

## Common Mistakes

- Using `success` alerts for information that isn't a success confirmation. "Here's a tip" is `info`, not `success`.
- Showing an error alert without telling the user how to fix the problem. Every error needs a recovery path.
- Placing the alert far from the content it relates to. A form error alert at the bottom of the page gets missed.
- Forgetting `aria-live` on dynamically added alerts. Screen reader users won't know the alert appeared.
- Using dismissible alerts for errors that the user hasn't resolved yet. Don't let users dismiss an error alert while the error still exists.

# Modal — Component UX Guidance

**Storybook:** `Overlay > Modal`
**Figma:** _(add your Figma component link)_

---

## When to Use

Use `Modal` when you need to interrupt the user's workflow to force a decision or acknowledgment before they can continue. Modals disable page content and focus attention on a single task.

**Use modals sparingly.** Every modal is an interruption. Before reaching for one, ask whether the information could live inline, in an `Alert`, or on its own page.

Good use cases:
- Confirming a destructive or irreversible action ("Delete this project?")
- Forcing acknowledgment before continuing ("Your session will expire soon")
- Displaying supplemental context without navigating away (a privacy policy during signup)

---

## Variants

| Variant | When to use |
|---------|-------------|
| `sm` | Simple confirmation with one or two short sentences and action buttons. |
| `md` | Default. Moderate content with a clear heading, body text, and actions. |
| `lg` | Longer explanatory content or content that would scroll at smaller sizes. |
| `fullscreen` | Complex flows that need maximum space. Use rarely. If it needs fullscreen, it might belong on its own page. |

---

## Do

- Use a clear heading that explains the purpose. "Delete project?" is better than "Are you sure?"
- Use specific button labels. "Delete project" and "Keep project" beats "Yes" and "Cancel."
- Keep content short. If it requires scrolling, consider a larger variant or a separate page.
- Place the primary action on the right (or bottom on mobile). Place the secondary/cancel action on the left.
- Return focus to the triggering element when the modal closes.

---

## Avoid

- Avoid surprising users with modals on page load. Modals should be triggered by a user action (except session timeout warnings).
- Avoid multi-step flows inside a modal. If a task has multiple steps, it belongs on its own page.
- Avoid form fields, accordions, or other complex components inside modals. They don't scale well on mobile and users lose context.
- Avoid stacking modals. Never open a modal from within a modal.
- Avoid using modals for error, success, or warning messages that relate to a form field. Use inline feedback instead.

---

## States

| State | Trigger | Notes |
|-------|---------|-------|
| Closed | Default | Modal not visible. Page content interactive. |
| Open | User action triggers modal | Overlay dims page content. Focus trapped inside modal. |
| Forced action | `data-force-action` or equivalent prop | Close button hidden. User must choose an action. Use for session timeouts or required acknowledgments only. |

---

## Accessibility

- **Focus trap:** When the modal is open, keyboard focus must stay inside the modal. Tab should cycle through focusable elements within the modal, never escaping to the page behind.
- **Focus on open:** Move focus to the modal container or the first focusable element when the modal opens.
- **Focus on close:** Return focus to the element that triggered the modal.
- **Label the modal:** Use `aria-labelledby` pointing to the modal heading so screen readers announce the title on open.
- **Describe the modal:** Optionally use `aria-describedby` pointing to the body text for additional context.
- **Close button placement:** The visible close button (X) should appear top-right visually, but place it last in the DOM so screen readers reach the content first.
- **Escape key:** Pressing Escape should close the modal (unless forced action is required).
- **Scroll lock:** Prevent the page behind from scrolling while the modal is open.

---

## Pairings

- `Modal` + `Button (destructive)` — confirmation before irreversible actions
- `Modal` + `Button (primary)` + `Button (secondary)` — standard decision pair
- `Alert` instead of `Modal` — for page-level success, error, or warning messages that don't need to block interaction

---

## Common Mistakes

- Using vague button labels like "Yes" and "No." Always label actions with what will happen: "Delete" and "Keep."
- Forgetting to trap focus. Keyboard users will tab behind the modal into invisible page content.
- Forgetting to return focus to the trigger on close. The user's position in the page gets lost.
- Using a modal for content that should be inline. If the user doesn't need to stop everything to see it, it's not a modal.
- Allowing the page behind to scroll while the modal is open. Disorienting, especially on mobile.

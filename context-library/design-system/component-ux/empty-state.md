# EmptyState — Component UX Guidance

**Storybook:** `Data > EmptyState`
**Figma:** _(add your Figma component link)_

---

## When to Use

Use `EmptyState` whenever a view, list, or container has no content to display. Empty states are an opportunity to guide the user toward their next action rather than showing a blank screen.

**Always use the `EmptyState` component.** Don't build custom empty states for individual features. Consistency matters.

---

## Variants

| Variant | When to use |
|---------|-------------|
| `default` | Explains why the area is empty. No prominent action needed (e.g., a filtered list with no matches). |
| `with-action` | Explains why the area is empty and provides a primary action to fix it (e.g., "No projects yet. Create your first project."). |

---

## Do

- Explain why the area is empty in plain language. "No notifications yet" is better than "No data."
- Include a next action whenever there is one. "Create your first project" is better than just "No projects."
- Match the tone to the context. A first-use empty state should feel welcoming. A no-results empty state should feel helpful.
- Use the empty state to teach. If this is the user's first time in a section, briefly explain what they'll see here once there is content.
- Use the `EmptyState` component inside the container where content would normally appear (inside a `DataTable`, inside a card group, inside a list).

---

## Avoid

- Avoid blank screens. Every empty container should have an `EmptyState`. No exceptions.
- Avoid generic messages like "No data available" or "Nothing to see here." Be specific about what's missing and why.
- Avoid illustrations or icons that don't add meaning. A decorative graphic shouldn't distract from the message.
- Avoid multiple CTAs in an empty state. One clear next action. If there are genuinely multiple paths, prioritize.

---

## Context Variants

Different empty states need different messages depending on how the user got there:

| Context | Message approach | Example |
|---------|-----------------|---------|
| First use (no data yet) | Welcome + explain + action | "No projects yet. Create your first project to get started." |
| No search results | Acknowledge query + suggest fix | "No results for 'onboarding.' Try a different search term or clear your filters." |
| No filter results | Acknowledge filters + offer reset | "No items match your current filters. [Clear filters]" |
| Error loading | Explain failure + offer retry | "We couldn't load your notifications. [Try again]" |
| Permission restricted | Explain restriction + next step | "You don't have access to this section. Contact your admin to request access." |

---

## Accessibility

- The empty state message should be visible and readable by screen readers. Don't hide it with `aria-hidden`.
- If the empty state includes an action button, it should be keyboard focusable and labeled clearly.
- If the empty state replaces a list or table, ensure the container still has its accessible role (e.g., the table structure should remain, with the empty state inside the `<tbody>`).
- If the empty state appears after a user action (like a search with no results), consider using `aria-live="polite"` to announce it.

---

## Pairings

- `DataTable (empty)` + `EmptyState` — inside the table body when there are no rows
- `EmptyState (with-action)` + `Button (primary)` — the primary CTA to populate the empty area
- `EmptyState` + `Alert` — if the empty state is caused by an error, pair with an error alert above

---

## Common Mistakes

- Showing a completely blank container with no explanation. Users don't know if the page is broken, still loading, or intentionally empty.
- Using the same generic message for every empty state in the product. Each context deserves a specific message.
- Forgetting the empty state for filtered or searched views. Designers spec the data-present state but forget to spec what happens when filters return zero results.
- Putting the CTA in the empty state but not elsewhere on the page. If "Create project" is the right action, it should also be accessible from the page header or nav, not only from the empty state.

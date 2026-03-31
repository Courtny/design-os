# UX Spec: Notifications list empty state (example)

**Author:** Design OS (example)  
**Date:** 2026-03-31  
**Status:** Example (calibration)  
**Brief:** _N/A — pattern reference_  
**Figma:** _[link when available]_

**Pattern references:** [Primer — Empty states](https://primer.style/product/ui-patterns/empty-states/) (Blankslate anatomy: graphic, primary text, secondary text, actions). Storybook remains production truth when names differ.

---

## Overview

When a user opens Notifications and has no notifications yet, show a single empty state that explains why the surface is empty, sets expectations, and offers one clear next step. This spec is intentionally small: one surface, one primary action, no data-fetch errors.

---

## Components Used

| Component | Storybook Path | Variant / Props Used | Notes |
|-----------|----------------|----------------------|-------|
| `EmptyState` | Feedback > EmptyState | `variant="marketing"`, optional `border` | Maps to Blankslate-style layout: optional illustration slot, title, description, primary + optional secondary link |
| `Button` | Actions > Button | `primary` | Single primary CTA |
| `Link` | Navigation > Link | `variant="subtle"` | Secondary action below primary |

_New patterns (not in Storybook):_ None for v1.

---

## Behavior

### Notifications — no notifications yet

**Default state:** User sees the notifications page chrome (title, toolbar if any) and a centered empty state below. No rows, no pagination.

**Interactions:**

| User action | System response |
|-------------|----------------|
| User loads `/notifications` with zero notifications | Empty state renders with illustration, title, description, primary button "Go to your inbox" |
| User clicks primary CTA | Navigate to `/inbox` (or configured default next step) |
| User clicks secondary link "Learn how notifications work" | Open help article in same tab or new tab per product convention |

---

## States

### EmptyState (first use)

| State | Trigger | Appearance | Notes |
|-------|---------|------------|-------|
| Default | Zero notifications, no error | Illustration + welcoming title + short description + primary CTA + optional secondary text link | Graphic should support the goal of the feature, not feel decorative-only (see Primer: intentional graphics) |
| Loading | List is fetching | Prefer skeleton rows or page-level spinner; do not flash empty state then replace | If empty state appears only after confirmed empty response, no loading inside Blankslate |
| Error | Fetch failed | Do not use playful illustration. Use alert-style graphic or icon. Title summarizes failure; secondary explains recovery | Per Primer: error empty states should not try to "delight" |

---

## Error States

_Write out messages. No vague "Something went wrong" without next steps._

| Error condition | User sees |
|-----------------|-----------|
| Notifications could not be loaded (server or network) | **Title:** "Notifications couldn't be loaded." **Secondary:** "Try again in a few minutes. If this keeps happening, contact support." **Primary action:** "Retry" |
| Partial outage (degraded) | Follow team degraded-experience pattern; empty state may be replaced by banner + reduced list |

Avoid obscure error codes in primary copy; include codes only when useful for support or diagnostics (aligned with Primer empty-state copy guidance).

---

## Empty States

| Context | Primary text | Secondary text | Primary action | Secondary action |
|---------|--------------|----------------|----------------|------------------|
| First use — feature never used | "You're all caught up" | "When someone mentions you or assigns you work, it will show up here." | "Go to your inbox" | "Learn how notifications work" |
| Filter returns zero (if filters exist later) | "No notifications match your filters" | "Try changing or clearing filters to see more." | "Clear filters" | — |

---

## Microcopy

| Element | Copy |
|---------|------|
| Page title | Notifications |
| Empty state title | You're all caught up |
| Empty state description | When someone mentions you or assigns you work, it will show up here. |
| Primary CTA | Go to your inbox |
| Secondary link | Learn how notifications work |

---

## Responsive Behavior

| Breakpoint | Behavior change |
|------------|-------------------|
| Mobile (< 768px) | Empty state stacks vertically; illustration scales down; tap targets stay ≥ 44px |
| Tablet / Desktop | Same content; max-width on text block for readability |

---

## Accessibility

- **Focus order:** Page title → primary button → secondary link (skip decorative illustration for Tab).
- **Keyboard:** Primary and secondary actions are focusable and activatable with Enter / Space.
- **ARIA:** Illustration is `aria-hidden="true"` if decorative; if the image conveys meaning, provide short `alt` text.
- **Color contrast:** Title and body meet WCAG AA for text; primary button meets contrast for text and focus ring.
- **Screen readers:** Announce the empty region as the main content for the list (e.g. `role="region"` with `aria-labelledby` pointing at the title).

---

## Out of Scope (v1)

- Bulk actions, pagination, or sample data.
- Marketing-style first-time onboarding modal in addition to this empty state.
- Custom illustrations beyond the design system illustration set.

---

## Open Questions

| Question | Owner | Due |
|----------|-------|-----|
| Should secondary link open help in a new tab? | Content design | TBD |

---

## Revision History

| Date | Change | Author |
|------|--------|--------|
| 2026-03-31 | Example spec for Design OS calibration | Design OS |

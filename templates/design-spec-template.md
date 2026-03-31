# UX Spec: [Feature Name]

**Author:**
**Date:**
**Status:** Draft / In Review / Approved / Shipped
**Brief:** _[link to brief or outputs/briefs/]_
**Figma:** _[direct link to approved frame]_

---

## Overview

_One or two sentences: what this feature does and why it exists._

---

## Components Used

_List every Storybook component used in this spec. Match names exactly._

| Component | Storybook Path | Variant / Props Used | Notes |
|-----------|---------------|----------------------|-------|
| `TextInput` | Forms > TextInput | `with-label`, `with-error` | |
| `Button` | Actions > Button | `primary`, `isLoading` | |
| | | | |

_New patterns (not in Storybook): [list here if any]_

---

## Behavior

### [Screen or Flow Name]

**Default state:**
_Describe what the user sees on first load._

**Interactions:**

| User action | System response |
|-------------|----------------|
| | |
| | |

---

### [Next Screen or Flow]

_(Repeat section as needed)_

---

## States

For each interactive element, document all states:

### [Component or section]

| State | Trigger | Appearance | Notes |
|-------|---------|-----------|-------|
| Default | Initial load | | |
| Loading | Action in progress | Spinner inside button; button disabled | Preserve layout width |
| Success | Action completes | Toast notification | See `Toast > success` |
| Error | Validation or server error | Error message below input | See error messaging below |
| Empty | No results / no data | `EmptyState` component | See empty state below |
| Disabled | [condition] | Reduced opacity | |

---

## Error States

_Write out every error message. Do not leave placeholders._

| Error condition | User sees |
|----------------|-----------|
| Required field empty | "[Field name] is required." |
| Invalid email format | "Enter a valid email address." |
| Server error | "Something went wrong. Try again or contact support." |

---

## Empty States

_What does the user see when there's no content?_

| Context | Message | Action |
|---------|---------|--------|
| First use (no data yet) | "[Explanation of empty state]" | [Primary CTA] |
| No search results | "No results for "[query]"" | Clear filters |

---

## Microcopy

_All visible text. No placeholders._

| Element | Copy |
|---------|------|
| Page title | |
| Primary CTA | |
| Input placeholder | |
| Helper text | |
| Success message | |
| Cancel confirmation | |

---

## Responsive Behavior

| Breakpoint | Behavior change |
|------------|----------------|
| Mobile (< 768px) | |
| Tablet (768–1024px) | |
| Desktop (> 1024px) | |

---

## Accessibility

- **Focus order:** _[describe tab order for the main flow]_
- **Keyboard interactions:** _[any non-standard keyboard shortcuts or focus traps]_
- **ARIA notes:** _[any `aria-label`, `aria-live`, `role` attributes not handled by components]_
- **Color contrast:** _[call out any custom colors not in the design system tokens]_
- **Screen reader notes:** _[anything a screen reader user needs that isn't obvious from the visual]_

---

## Out of Scope (v1)

_Be explicit. Prevents scope creep._

-
-

---

## Open Questions

_Unresolved at time of writing. Assign owners._

| Question | Owner | Due |
|----------|-------|-----|
| | | |

---

## Revision History

| Date | Change | Author |
|------|--------|--------|
| | Initial draft | |

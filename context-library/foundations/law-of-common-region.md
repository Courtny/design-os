# Context File: Law of Common Region

**Status:** Core Interaction Principle  
**Tagline:** "A shared space implies a shared purpose."

---

## Executive Summary

The **Law of Common Region** states that elements tend to be perceived as belonging to the same group when they are enclosed within a clearly defined boundary. A box, card, background color, or border communicates containment — and containment communicates relationship. This is one of the most powerful tools in a designer's layout toolkit because it works without labels.

---

## Background

The Law of Common Region is one of the Gestalt principles of visual perception, formalized by Palmer (1992) as an extension of earlier Gestalt work. Where the Law of Proximity groups elements by *distance*, Common Region groups them by *enclosure*. The two often work together, but Common Region tends to create stronger groupings when visual boundaries are clear.

> See also: [`gestalt-principles.md`](gestalt-principles.md) for the full Gestalt framework.

---

## Why It Matters for the Design OS

1. **Cards are the most literal application.** Every card in our component library uses Common Region to say "these pieces of content belong to the same entity." The card boundary is doing heavy lifting.
2. **Enclosure creates hierarchy.** Nested containers (a form field group inside a form section inside a page) use Common Region to communicate structural depth without relying on labels alone.
3. **Background color is a boundary.** A shaded table row, a highlighted input field, a panel with a different background — all of these create regions that users naturally interpret as grouped.

---

## Implementation Guidelines

| Pattern | Application |
| :--- | :--- |
| **Cards for entity-level grouping** | Use the card component to wrap content that belongs to a single entity (a product, a user, a task). |
| **Form sections** | Group related form fields with a subtle container or dividing line. Don't rely on proximity alone for long forms. |
| **Panel vs. background** | Use a panel (distinct background) to separate a sidebar, modal, or settings section from primary content. |
| **Avoid decorative boundaries** | Don't add borders or backgrounds that don't signal a meaningful group. False regions confuse users. |
| **Nested regions** | Use sparingly. More than 2–3 levels of nesting creates cognitive overhead and visual noise. |

---

## Common Region vs. Proximity

Both create groupings, but they're not equivalent:
- **Proximity** groups by distance — elements that are close together look related
- **Common Region** groups by enclosure — elements inside a shared boundary look related, even if they're not especially close

Common Region creates a *stronger* grouping signal. Use it when the relationship matters and proximity alone wouldn't be clear enough.

---

## Related Principles

- **Gestalt Principles:** Common Region is part of the Gestalt family; see `gestalt-principles.md` for the full set.
- **Law of Proximity:** The complementary spatial grouping principle.
- **Chunking:** Common Region is the visual mechanism that makes chunks perceivable.
- **Cognitive Load:** Clear regional boundaries reduce extraneous load by communicating structure visually.

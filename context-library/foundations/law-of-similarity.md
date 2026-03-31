# Context File: Law of Similarity

**Status:** Core Interaction Principle  
**Tagline:** "Look alike, act alike."

---

## Executive Summary

The **Law of Similarity** states that the human eye tends to perceive similar elements as belonging to the same group or category, even if those elements are physically separated. In UI design, similarity is one of the most powerful tools for communicating type and relationship without labels. Elements that share shape, color, size, or treatment are assumed to behave the same way — so visual consistency is not just aesthetic, it's functional.

---

## Background

The Law of Similarity is one of the core Gestalt principles of perceptual organization. It was established alongside Proximity, Prägnanz, and Closure in the early 20th century. The insight: the visual system groups elements by shared properties before it processes their content. You see "a row of circles" before you read what each circle says.

> See also: [`gestalt-principles.md`](gestalt-principles.md) for the full Gestalt framework.

---

## Why It Matters for the Design OS

1. **Consistency communicates type.** All primary buttons should look the same. All links should look the same. All destructive actions should look the same. Visual similarity tells users "these things are the same kind of thing."
2. **Inconsistency creates confusion.** If two elements look similar but behave differently, users will expect them to behave the same — and be confused when they don't. Visual similarity makes an implicit promise.
3. **Similarity can override proximity.** Users will group elements that look alike even if they're on opposite sides of the screen, and will *not* group adjacent elements that look different. Similarity is a stronger grouping signal than proximity when the visual difference is strong.

---

## Implementation Guidelines

| Pattern | Application |
| :--- | :--- |
| **Consistent button styles** | Use the same visual treatment for all instances of the same button type. Don't create "one-off" variants. |
| **Link styling** | All inline links should look identical. Color, underline, weight — make the promise uniform. |
| **Data table rows** | Alternating row colors (zebra striping) use similarity within rows to create horizontal scan lines. |
| **Icon families** | Use a single icon library and style consistently. Mixing filled and outline icons from different families breaks similarity grouping. |
| **Form element consistency** | All text inputs, all dropdowns, all checkboxes — each type should be visually identical to every other instance of that type. |

---

## Similarity as Affordance

When users encounter a new element, they scan for visual similarity to something they already know. A new button that looks like every other button they've interacted with inherits the affordance of buttons. This is why deviating from familiar UI patterns has a cost: you break the similarity signal that transfers knowledge.

> **The Design OS Motto:** *Visual consistency is a promise. Break it intentionally or not at all.*

---

## Related Principles

- **Gestalt Principles:** Similarity is one pillar of the full Gestalt framework; see `gestalt-principles.md`.
- **Law of Proximity:** The complementary spatial grouping principle.
- **Von Restorff Effect:** The inverse — the element that breaks similarity is the one users remember.
- **Mental Models:** Similarity supports mental model transfer from other products; inconsistency breaks it.
- **Affordance:** Similar-looking elements share perceived affordances — this is a feature, not a side effect.

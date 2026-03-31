# Context File: Law of Uniform Connectedness

**Status:** Core Interaction Principle  
**Tagline:** "A line between two things says they belong together."

---

## Executive Summary

The **Law of Uniform Connectedness** states that elements that are visually connected are perceived as more strongly related than elements that are not connected — even when other Gestalt signals (proximity, similarity) suggest otherwise. A line, a border, a shared color fill, or a connecting graphic creates a relationship that users trust. Connectedness is the most explicit grouping signal available in visual design.

---

## Background

The Law of Uniform Connectedness was proposed by Stephen Palmer and Irvin Rock (1994) as an addition to the original Gestalt principles. Their research showed that elements joined by a uniform visual link (a line, a region, a frame) were perceived as grouped more strongly than elements linked only by proximity or similarity. It is sometimes called the "strongest" Gestalt grouping cue because it is explicit rather than inferred.

> See also: [`gestalt-principles.md`](gestalt-principles.md) for the full Gestalt framework.

---

## Why It Matters for the Design OS

1. **Visual connections imply interaction.** A line between two nodes in a diagram, a thread connecting messages in a conversation, a breadcrumb trail — each of these uses connectedness to signal that items are sequentially or causally related.
2. **Borders create ownership.** A border around a group of form fields says "these belong to the same step." Remove the border and the grouping weakens, even with identical spacing.
3. **Connected elements must behave consistently.** If two elements are visually connected, users will assume they're functionally related. Don't visually connect elements that aren't actually related.

---

## Implementation Guidelines

| Pattern | Application |
| :--- | :--- |
| **Progress steps** | Connect step indicators with a line or track to signal sequential relationship. A disconnected set of circles reads as separate items, not a sequence. |
| **Form field grouping** | A subtle border or shared background around related fields creates a stronger group than spacing alone. |
| **Relationship diagrams** | Use connecting lines to show explicit relationships between nodes. Don't rely on proximity when the relationship needs to be unambiguous. |
| **Navigation breadcrumbs** | Separators (/ or >) visually connect the trail while implying direction. The connection communicates hierarchy. |
| **Tabs and their content** | The selected tab should visually connect to the content panel below it (shared border edge, shared background). Disconnected tabs feel like separate elements, not content switchers. |

---

## Connectedness vs. Proximity

Proximity groups by *distance* — elements close together are assumed related. Connectedness groups by *link* — elements with a visible connection are assumed related. Connectedness is more explicit and more powerful:
- Proximity works at a glance without any visual artifacts
- Connectedness requires a visual element (line, border, fill) but creates a stronger, more unambiguous grouping

Use proximity for soft grouping; use connectedness when the relationship needs to be unambiguous.

> **The Design OS Motto:** *If you draw a line between things, you're making a promise about their relationship.*

---

## Related Principles

- **Gestalt Principles:** Uniform Connectedness is part of the Gestalt family; see `gestalt-principles.md`.
- **Law of Proximity:** The softer, distance-based grouping principle — often used together with connectedness.
- **Law of Common Region:** Enclosure is a form of connectedness; both create explicit groupings.
- **Affordance:** Visual connections can imply that elements interact (e.g., connecting a slider to its value label).

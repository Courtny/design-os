# Context File: Law of Prägnanz

**Status:** Core Interaction Principle  
**Tagline:** "The brain always bets on simple."

---

## Executive Summary

The **Law of Prägnanz** (German for "conciseness" or "precision") states that people perceive and interpret ambiguous or complex images as the simplest, most regular form possible — because simple interpretations require the least cognitive effort. In UI design, this means users will always try to apply the simplest, most familiar mental model to your interface, whether that interpretation is accurate or not. If your design is ambiguous, users will simplify it wrong.

---

## Background

Prägnanz is the foundational principle of Gestalt psychology, from which all other Gestalt laws derive. Wertheimer, Köhler, and Koffka developed it in the early 20th century. The core claim: the visual system is not a passive recorder — it actively organizes perception toward the "good figure" (German: *gute Gestalt*), which is the simplest, most stable, most regular interpretation available.

> See also: [`gestalt-principles.md`](gestalt-principles.md) for the full Gestalt framework.

---

## Why It Matters for the Design OS

1. **Users simplify first, question later.** If an icon could mean two things, users will pick the simpler interpretation. If a layout could imply two structures, users will assume the simpler one. Design for the simplest reading you want users to have.
2. **Ambiguity costs trust.** When users simplify incorrectly and then discover the interface works differently than they assumed, trust breaks. Clarity is not just friendliness — it's accuracy.
3. **Complexity doesn't teach.** You can't use interface complexity to train users toward a more nuanced mental model. They'll simplify it anyway. If a pattern needs to be complex, make that complexity explicit and guided.

---

## Implementation Guidelines

| Strategy | Application |
| :--- | :--- |
| **Reduce visual noise** | Every element that doesn't contribute to meaning competes with elements that do. Remove it. |
| **Use familiar shapes and patterns** | Prägnanz means users prefer regular, symmetric, familiar forms. Don't use irregular or custom shapes for functional UI elements. |
| **Make structure unambiguous** | If a layout could be read as 2 columns or 3, users will pick one — probably the wrong one. Add spacing, dividers, or labels to clarify. |
| **Align with simple mental models** | Design around the simplest accurate mental model for the system. Fight the urge to expose underlying complexity. |
| **Test for misinterpretation** | During usability testing, ask users to describe what they see before they interact. Prägnanz failures show up as incorrect initial descriptions. |

---

## Prägnanz and Icon Design

Icons are particularly vulnerable to Prägnanz failures. Users will interpret any icon as the simplest, most common meaning they associate with that shape. A hamburger menu icon works because there's a single dominant interpretation. A custom icon that "kind of looks like" a common icon will be mis-read as that icon. When in doubt, use a label.

> **The Design OS Motto:** *Design the simplest version of the right idea.*

---

## Related Principles

- **Gestalt Principles:** Prägnanz is the root principle; all other Gestalt laws are expressions of it.
- **Mental Models:** Prägnanz explains why users apply their existing mental models so persistently, even when they're wrong.
- **Cognitive Load:** The push toward simplicity is the brain minimizing load. Designs that fight this tendency increase load.
- **Occam's Razor:** The design equivalent — the simplest sufficient explanation is the best one.

# Context File: Law of Proximity

**Status:** Core Interaction Principle  
**Tagline:** "Near means related. Far means separate."

---

## Executive Summary

The **Law of Proximity** states that objects placed near each other are perceived as belonging to the same group. This is one of the oldest and most reliable Gestalt principles. In practice: if two elements are close together, users will assume they're related — whether or not they actually are. Spacing is not just aesthetic; it is *meaning-making*.

---

## Background

The Law of Proximity was established by Gestalt psychologists in the early 20th century as part of a broader theory of perceptual organization. The brain is constantly looking for patterns and groupings to reduce cognitive effort. Proximity provides one of the most effortless grouping cues because it requires no labels, no color, and no explicit structure.

> See also: [`gestalt-principles.md`](gestalt-principles.md) for the full Gestalt framework.

---

## Why It Matters for the Design OS

1. **Spacing is communication.** The distance between a label and its input, a button and its context, a heading and its section — all of these carry implicit meaning. Inconsistent spacing sends incorrect signals.
2. **Proximity beats labels.** A help text placed 40px below an input field will read as unrelated to it. The same text at 8px reads as directly associated. Don't fight proximity with labels.
3. **Layout creates invisible relationships.** Two elements that happen to share a row or column will be grouped by users even if they're not related. Watch for accidental proximity in grid layouts.

---

## Implementation Guidelines

| Pattern | Application |
| :--- | :--- |
| **Form labels and inputs** | Keep labels within 4–8px of their input. Never let another element slip between them. |
| **Related action buttons** | Group buttons that act on the same object. Separate destructive actions (Delete) from constructive ones (Save, Submit). |
| **Heading to content** | A section heading should be closer to the content it introduces than to the section above it. Roughly 2:1 spacing ratio. |
| **Card internals** | Within a card, tighter spacing between related items (author + date) and looser spacing between distinct items (title vs. body). |
| **Navigation grouping** | Group nav items by task similarity with spacing, not just visual separators. Proximity communicates category. |

---

## The 2:1 Spacing Rule

A reliable heuristic: the space *after* a section heading should be roughly half the space *before* it. This makes the heading feel attached to what follows, not floating between sections. The same principle applies at any scale — a button label should be closer to its icon than to the next button.

---

## Related Principles

- **Gestalt Principles:** Proximity is one pillar of the full Gestalt framework; see `gestalt-principles.md`.
- **Law of Common Region:** Proximity and enclosure often work together to create groupings; Common Region is stronger when boundaries are explicit.
- **Chunking:** Proximity is the visual mechanism that makes spatial chunks apparent.
- **Cognitive Load:** Correct proximity reduces the work of interpreting structure — users don't need to read labels if layout is doing its job.

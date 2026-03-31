# Context File: Cotten's Many Doors

**Status:** Active | **Category:** Navigation & Discoverability  
**Author:** Courtny Cotten  
**Tagline:** "A room with one door is a trap. A room with many doors is a hub."

---

## Executive Summary

**Cotten's Many Doors** is a navigation and discoverability principle: if a feature is vital to the user's success, the system must provide multiple, redundant pathways to reach it — each appropriate to the user's current context and mental state.

Traditional minimalism often mistakes "cleanliness" for "usability." This principle posits that a user's intent shouldn't be a scavenger hunt. We build hubs, not traps. The goal is not more UI; it's more *relevant* entry points placed where the user's friction is highest.

---

## The Philosophy

Discoverability is a first-class design concern, not a polish-phase afterthought. When a feature has only one path, adoption depends entirely on whether users encounter that path. When a feature has many doors, users find it through the path that matches how they're already thinking.

> "A room with one door is a trap; a room with many doors is a hub. In digital product design, we build hubs."

---

## The Door Typology

Use the **Entry Point Matrix** during wireframing any new feature. Every significant feature should have at least two door types. High-value features should have all four.

| Door Type | Description | Example |
| :--- | :--- | :--- |
| **The Grand Entrance** | The primary, most obvious location in global navigation. | The "New Post" button in the sidebar. |
| **The Shortcut** | High-efficiency entry for power users. | `Cmd + K` → "New Post" or a dedicated hotkey. |
| **The Contextual Side-Door** | Appears when the user is already interacting with related data. | Right-clicking an image to "Create New Post with this image." |
| **The Safety Net** | Appears when the user is stuck or in an empty state. | A "Start your first post" button in a blank feed. |

---

## Three Rules of Application

Many Doors only works when the doors are well-managed. Without these rules, it becomes noise.

1. **Uniformity of Destination.** No matter which door a user enters, the resulting destination must be identical. Redundancy should lead to the same experience, not fragmented versions of it.
2. **Visual Weighting.** There are many doors, but only one Grand Entrance. Use size, color, and contrast to signal the official path while keeping secondary doors subtle and contextual.
3. **Proximity of Need.** Place doors where friction is highest. If the user is looking at a report, "Export" and "Share" belong within eye-line of that data — not buried in a settings menu.

---

## Success Indicators

- **Reduced Time-to-Action:** Users spend less time scanning menus looking for a specific function.
- **High Feature Adoption:** New users discover secondary features without a guided tour or documentation.
- **Workflow Flexibility:** Power users and novices both report feeling "fast" in the tool.

---

## Warning Signs: The "Funhouse" Effect

| Anti-Pattern | What It Looks Like | Fix |
| :--- | :--- | :--- |
| **Choice Paralysis** | Every button is the same color and size — no clear Grand Entrance. | Apply visual hierarchy. One primary, the rest secondary. |
| **Inconsistent Labeling** | A door is called "Create" in one place and "New Item" in another. | Naming must be immutable across all entry points. |
| **UI Clutter** | Too many physical buttons competing in the header. | Move secondary doors into overflow menus or contextual hover states. |

---

## Related Principles

- **Jakob's Law:** Users expect paths they already know from other products. Many Doors works best when the Grand Entrance is where users habitually look.
- **Hick's Law:** More doors doesn't mean better — only *relevant* entry points reduce decision time. Irrelevant doors add noise.
- **Selective Attention:** Users only see what's on their task path. Contextual Side-Doors and Safety Nets work because they appear precisely where attention already is.
- **Affordance:** Each door type must look like a door — interactive, labeled, and clearly separate from static content.
- **Choice Overload:** Many Doors is an entry-point strategy, not a permission to surface all options simultaneously. Apply visual weighting to prevent paralysis.

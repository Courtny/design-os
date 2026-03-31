# Design OS: The 80/20 Framework (Pareto)

Use this framework to steer a Design Operating System around the **Pareto principle**: roughly 80% of user value, visual impact, and functional stability comes from about 20% of design effort. The goal is to find that **vital few**, execute it with focus, and **satisfice** the useful many so you stop pixel-pushing margins and start moving needles that matter for the product and the user.

---

## Core philosophy

We assume most outcomes cluster on a small slice of work. We identify that slice and protect it. Everything else gets good enough, automation, or a deliberate no.

---

## Operational pillars

### 1. The critical path (UX)

- **The 20%:** The primary user flow (checkout, onboarding, core task).
- **The 80% rule:** If the core flow is solid, users often forgive minor UI issues on settings or secondary pages.
- **Action:** Prioritize **gold path** usability over edge-case perfection.

### 2. High-leverage UI (systems)

- **The 20%:** Typography, color palette, and spacing grids.
- **The 80% rule:** Those foundations drive most of how the product *feels*. If they are weak, custom illustration rarely fixes the brand.
- **Action:** Lock foundational tokens before building complex components.

### 3. Feature prioritization (product)

- **The 20%:** Features that most active users touch every day.
- **The 80% rule:** A large share of tech debt and support pain often traces to a small set of low-value or bloated features.
- **Action:** Say no to most requests so the core slice stays world-class.

---

## Decision matrix

When you pick up a design task, place it:

| Dimension | Vital ~20% | Trivial ~80% |
| :--- | :--- | :--- |
| **Effort** | High concentration, deep craft | High volume, busywork |
| **Impact** | Moves KPIs or core UX | Incremental or aesthetic-only |
| **Urgency** | Critical for launch | Nice to have |
| **Approach** | **Obsess** | **Automate, template, or defer** |

---

## Anti-patterns

- **Polishing the hidden:** Days on an empty state for a screen almost no one sees.
- **Premature optimization:** Multi-variant components before the feature is validated.
- **The perfection trap:** Delaying launch because a secondary icon is not perfect.

> Done beats perfect for the long tail. For the vital few, excellent is the bar.

---

## Implementation cadence

- **Weekly audit:** Scan the sprint. Are you spending most time on the slice that actually moves outcomes?
- **Quarterly pruning:** Find the small part of the UI that drives most confusion or support load; simplify or remove it.

---

## How the copilot uses this

When prioritization questions come up, this file pairs with [`refactoring-ui-principles.md`](refactoring-ui-principles.md), design principles in [`../design-system/principles.md`](../design-system/principles.md), and your product context. Prefer Storybook-backed patterns for the vital path; do not invent one-off systems when tokens and core flows are still unsettled.

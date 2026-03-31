# Hick's Law

> The time it takes to make a decision increases with the number and complexity of choices.

Formulated by William Edmund Hick in 1952 (and later refined by Ray Hyman). The relationship is logarithmic: doubling the number of options doesn't double decision time, but it still compounds. More importantly, too many options can trigger **decision avoidance** entirely — users abandon rather than choose.

---

## Core Principles

**Decision Fatigue** — Too many options lead to "analysis paralysis." Users stall, second-guess, or disengage. This is especially pronounced when choices feel consequential or irreversible.

**Simplicity** — Reducing choices reduces cognitive load. This doesn't mean fewer features; it means fewer choices presented at one time.

---

## Application

1. **Minimize choices in navigation** — Flat, long nav menus force users to read and evaluate every option. Group into 4-6 top-level categories and let users drill down rather than scanning all options at once.

2. **Progressive disclosure** — Break complex processes into multi-step flows rather than one large form. A 5-step checkout with 3 fields each is easier than a single-screen checkout with 15 fields. Users only process the choices in front of them.

3. **Highlight a recommendation** — Use "Suggested," "Most Popular," or "Recommended" labels to guide the user's attention when multiple plans, options, or configurations are offered. This doesn't remove choice; it reduces the perceived cost of choosing.

4. **Default to sensible defaults** — Pre-select the most common choice wherever reasonable. Users who want something else will change it; users who don't notice will be served well.

---

## What It Doesn't Mean

Hick's Law is not an argument for fewer features. It's an argument for **staged revelation** of complexity. A professional tool can have hundreds of options — they just shouldn't all be visible at once. Power users who need them will find them. New users shouldn't be confronted with them upfront.

---

## Related Foundations

- [`millers-law.md`](millers-law.md) — Miller's is about memory capacity; Hick's is about decision time. Both argue for chunking and simplification.
- [`80-20-framework.md`](80-20-framework.md) — Hick's Law is the UX argument for 80/20 scoping: surface the 20% of options users need most.
- [`nielsens-heuristics.md`](nielsens-heuristics.md) — H7 (flexibility and efficiency of use) addresses expert users who need full complexity; Hick's Law explains why novices shouldn't see it first.
- [`cottens-many-doors.md`](cottens-many-doors.md) — Many Doors' Visual Weighting rule is the practical Hick's Law mitigation: multiple entry points only work without decision overhead when one is clearly the Grand Entrance and the rest are subordinate

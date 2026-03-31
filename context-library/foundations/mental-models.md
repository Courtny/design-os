# Mental Models

> What a user believes they know about a system at hand.

Mental models are the internal representations users form about how something works. They're built from past experience, analogies, and observation — not from reading docs. Designing against the user's mental model is one of the most common sources of friction.

---

## Core Principles

**Expectation vs. Reality** — If a system doesn't behave the way a user expects, they become frustrated, confused, or lost. The gap between the user's mental model and the system's actual model is where UX problems live.

**Interface Mapping** — The UI should map to real-world concepts users already understand. A "folder" for file storage, a "trash can" for deletion, a "magnifying glass" for search. These work because they match existing mental models — not because they're literally accurate.

---

## Application

1. **Research first** — Perform user research to understand how your audience already perceives the problem. You can't design to a model you haven't observed. This is especially important when entering a new domain or serving non-technical users.
2. **Use metaphors that fit the user's background** — A financial app serving accountants can lean on ledger metaphors. A consumer app serving general users needs simpler, more universal mappings.
3. **Reinforce the model through system feedback** — Animations and transitions should confirm user expectations. An item moving to the trash when deleted reinforces the model; an item disappearing with no feedback breaks it.

---

## Common Mismatches to Watch For

- **Technical naming exposed in the UI** — Developers name things after implementation ("null state," "batch job," "API error"). Users don't have mental models for these.
- **Undo without confirmation** — Users expect destructive actions to warn before executing. Skipping confirmation breaks the "I'm in control" model.
- **Non-standard navigation patterns** — Back buttons that don't navigate back, save buttons that don't persist data, checkboxes styled as toggles. Each breaks a convention users carry from other products.
- **Progress indicators that lie** — A progress bar that jumps or pauses trains users to distrust system feedback.

---

## Related Foundations

- [`nielsens-heuristics.md`](nielsens-heuristics.md) — H2 (match between system and real world) and H4 (consistency and standards) are directly grounded in mental model theory
- [`jakobs-law.md`](jakobs-law.md) — Jakob's Law is essentially mental models applied at a product-ecosystem level
- [`affordance.md`](affordance.md) — Affordance is how visual form shapes the mental model of what an element does
- [`cottens-many-doors.md`](cottens-many-doors.md) — The Grand Entrance must be placed where users' existing mental model says navigation lives. Many Doors fails if the primary door is put somewhere users' prior product experience wouldn't lead them to look.

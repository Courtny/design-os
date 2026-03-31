# WCAG (Web Content Accessibility Guidelines)

> Standards from the W3C that ensure digital products are usable by people with a wide range of disabilities.

---

## The POUR Principles

- **Perceivable:** Information and UI components must be presentable in ways users can perceive. Nothing should be invisible to all their senses.
- **Operable:** UI components and navigation must be operable. The user must be able to use the interface.
- **Understandable:** Information and UI operation must be understandable.
- **Robust:** Content must be interpreted reliably by a wide variety of user agents, including assistive technologies.

---

## Core Requirements (AA Conformance)

1. **Contrast:** Minimum 4.5:1 ratio for normal text. 3:1 for large text (18px+ regular or 14px+ bold).
2. **Alt Text:** Provide text alternatives for all non-text content — images, icons, charts.
3. **Keyboard Navigation:** Every interactive element must be reachable and triggerable without a mouse.
4. **Color Independence:** Never use color as the only way to convey meaning. Pair color with a label, icon, or pattern (an error can't just be a red border).
5. **Focus States:** Never remove the default focus ring without providing a visible, high-contrast alternative. Focus must always be visible.

---

## Using These in Practice

Use WCAG as a **pre-handoff checklist** and as grounding for accessibility-related design decisions.

- **Specs:** Call out contrast ratios, alt text requirements, and keyboard behavior for each interactive component.
- **Critique:** Flag color-only states, missing focus styles, and icon-only controls without labels.
- **New patterns:** Check color independence and keyboard operability before proposing anything non-standard.
- **Error states:** An error message that's only red fails WCAG 1.4.1. It needs a label or icon alongside the color change.
- **Accessibility review:** The `/accessibility-review` skill runs against these criteria.

---

## Related Foundations

- [`nielsens-heuristics.md`](nielsens-heuristics.md) — H9 (error recovery) overlaps directly with color independence and error labeling requirements
- [`affordance.md`](affordance.md) — perceived affordance ties to keyboard operability; if an element doesn't look interactive, keyboard users skip it too
- [`fitts-law.md`](fitts-law.md) — touch target sizing (44x44px minimum) is both a Fitts's Law and WCAG 2.5.5 concern
- [`cognitive-load.md`](cognitive-load.md) — WCAG's "Understandable" principle maps directly onto reducing extraneous cognitive load

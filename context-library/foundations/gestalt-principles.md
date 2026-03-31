# Gestalt Principles

> The human eye perceives visual elements as a unified whole rather than individual parts.

Gestalt is German for "form" or "unified whole." These principles explain how users group, connect, and interpret visual information automatically — before conscious thought.

---

## Key Principles

**Proximity** — Elements close to each other are perceived as a group. Physical distance implies relationship. White space separates groups more powerfully than borders or color.

**Similarity** — Elements that look alike are perceived as related. Shape, color, size, and texture all signal grouping. Consistent button styles exploit this: same color = same priority.

**Closure** — The brain automatically fills in gaps to perceive a complete shape. Users don't need fully closed outlines to recognize forms — they complete partial shapes mentally. Progress rings and icon outlines rely on this.

**Continuity** — The eye follows the smoothest path when looking at lines or curves. Elements arranged on a line or curve are perceived as more related than elements that are not. Reading direction (left-to-right, top-to-bottom) is a continuity pattern.

---

## Application

1. **Use white space (proximity) to group related content sections** — a label above an input field, with more space below than above, visually binds the two. Don't add borders when spacing does the work.
2. **Use consistent colors and shapes (similarity) for all buttons of the same priority** — mixing shapes or colors within the same action tier breaks the similarity signal and forces users to re-evaluate.
3. **Align elements to create clear visual paths (continuity)** — left-aligned columns, consistent baseline grids, and left-edge alignment on form labels all reduce scan time.
4. **Rely on closure for lightweight iconography** — outline icons work because users complete the shape mentally. Overly detailed icons fight this and become noise.

---

## When It Breaks

- Overusing borders and dividers when proximity alone is sufficient creates visual clutter (violates H8 from Nielsen's heuristics).
- Inconsistent button styles within the same context break similarity — users slow down to evaluate rather than act.
- Centering mixed-length text blocks disrupts continuity; left-aligned text is almost always easier to scan.

---

## Related Foundations

- [`affordance.md`](affordance.md) — visual form communicates affordance, which Gestalt principles shape
- [`refactoring-ui-principles.md`](refactoring-ui-principles.md) — visual hierarchy and spacing rules build on proximity and similarity
- [`nielsens-heuristics.md`](nielsens-heuristics.md) — H8 (aesthetic and minimalist design) maps closely to Gestalt economy

# Fitts's Law

> The time to acquire a target is a function of the distance to and size of the target.

Paul Fitts formalized this in 1954. The model predicts that pointing time increases as distance grows and decreases as target size grows. On screens, this means tap and click targets need to be large enough and close enough to use comfortably — especially on mobile.

---

## Core Principles

**Target Size** — Larger targets are faster to acquire. A 44px tap target is meaningfully easier to hit than a 20px one, especially under any motor uncertainty (mobile, fatigue, users with motor impairments). Apple's HIG and Google's Material Design both use 44-48px minimum touch targets for this reason.

**Distance** — The further a target is from the user's current pointer or finger position, the longer it takes to reach. Group related actions. Don't make users travel across the screen to complete a single flow.

**Edges and Corners Are Infinite Targets** — Because the pointer cannot go past the edge of the screen, the edges and corners are effectively infinite in size in one dimension. Users can slam the mouse into a corner without overshooting. This makes screen edges ideal locations for frequently used, high-impact controls.

---

## Application

1. **Make primary action buttons larger than secondary ones** — The visual hierarchy of button size should match the hierarchy of action importance. A primary CTA should be the easiest thing to tap on the screen.
2. **Group related interactive elements together** — A form's label, input, and helper text should be physically close. Don't split confirm/cancel buttons to opposite sides of the screen when they're part of the same decision.
3. **Use screen edges and corners for high-frequency or high-impact actions** — macOS dock, Windows taskbar, mobile navigation bars. These are "free" targets because they require no precision to hit.
4. **Size touch targets to 44-48px minimum on mobile** — The visual size of an icon can be smaller, but the tappable area should extend to at least 44px. Use padding to increase target area without changing visual weight.

---

## The Accessibility Connection

Fitts's Law is the engineering rationale behind WCAG 2.5.5 (Target Size). A 24px minimum is a WCAG AA pass, but 44px is the practical recommendation for low-effort interaction. Users with motor impairments feel small targets acutely. Audit spacing around small icons (close buttons, inline actions, form checkboxes) before handoff.

---

## Related Foundations

- [`nielsens-heuristics.md`](nielsens-heuristics.md) — H7 (flexibility and efficiency of use) benefits from Fitts's optimization for frequent actions
- [`gestalt-principles.md`](gestalt-principles.md) — Proximity principle supports grouping related targets to reduce travel distance
- [`affordance.md`](affordance.md) — Target size affects perceived affordance: a tiny tap target doesn't feel clickable even if it is

# Context File: Occam's Razor

**Status:** Core Interaction Principle  
**Tagline:** "Don't add what you can remove."

---

## Executive Summary

**Occam's Razor** is the principle that among competing hypotheses or solutions, the one with the fewest assumptions should be selected. In design, it translates simply: don't add complexity unless it solves a real, demonstrated problem. The simplest solution that fully addresses the user's need is the best solution. Every added element, interaction, or feature carries a cost — cognitive load, maintenance burden, accessibility debt — and that cost must be justified.

---

## The Origin Story

Occam's Razor is named after William of Ockham, a 14th-century English Franciscan friar and philosopher who used the principle extensively in his logical writings. The formal statement: *"Entities should not be multiplied without necessity."* Einstein later rephrased it for engineering: *"Everything should be made as simple as possible, but not simpler."* The "but not simpler" clause is crucial — Occam's Razor is not an argument for oversimplification.

---

## Why It Matters for the Design OS

1. **Features accrete; they rarely self-remove.** Every feature added to a product increases the surface area users must understand. Occam's Razor is the counter-pressure against feature creep.
2. **Complexity compounds.** A slightly complex interaction combined with a slightly complex form combined with a slightly complex navigation creates an overwhelming experience. Simplicity at each decision compounds into a dramatically better whole.
3. **The simplest explanation is usually right.** When debugging a confusing user behavior in research, start with the simplest explanation (the label was unclear) before reaching for complex ones (users don't understand the concept).

---

## Implementation Guidelines

| Decision Point | Apply Occam's Razor By |
| :--- | :--- |
| **Adding a new UI element** | Ask: does removing this element break the user's ability to accomplish their goal? If no, remove it. |
| **Adding a new step to a flow** | Ask: is there a version of this flow with fewer steps that achieves the same outcome? Start there. |
| **Designing a new component** | Ask: does an existing component handle this case? Use it. Only design new patterns when existing ones genuinely can't cover the need. |
| **Writing microcopy** | Ask: is there a shorter version of this that says the same thing? Use it. |
| **Choosing between two design approaches** | Ask: which requires fewer new patterns, fewer new mental models, fewer exceptions? That's the better candidate. |

---

## Occam's Razor vs. 80/20

These principles are complementary, not competing:
- **Occam's Razor** asks "is this element necessary?" — it's about simplicity and the cost of complexity
- **The 80/20 principle** asks "does this element serve most users?" — it's about prioritization and impact

A feature can pass the 80/20 test (serves 80% of users) but still violate Occam's Razor (a simpler version would serve those same 80% users just as well).

> **The Design OS Motto:** *Add nothing without cause. Remove everything you can.*

---

## Related Principles

- **Cognitive Load:** Occam's Razor is the design practice that manages extraneous cognitive load.
- **Law of Prägnanz:** Users prefer the simplest interpretation — design should offer it, not fight it.
- **Tesler's Law:** Complexity can be reduced in presentation but not eliminated entirely. Occam's Razor tells you where to stop simplifying.
- **80/20 Framework:** [`80-20-framework.md`](80-20-framework.md) — the prioritization partner to Occam's Razor.

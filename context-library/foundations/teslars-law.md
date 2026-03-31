# Context File: Tesler's Law

**Status:** Core Interaction Principle  
**Tagline:** "Complexity can't be eliminated — only moved."

---

## Executive Summary

**Tesler's Law**, also known as the Law of Conservation of Complexity, states that every system has a certain amount of inherent complexity that cannot be reduced — it can only be shifted from one place to another. If you simplify the user interface by hiding complexity, that complexity moves somewhere else: into the backend, into the setup process, into documentation, or into a power user interface. The designer's job is not to eliminate complexity but to decide *who carries it* and *when they have to deal with it*.

---

## The Origin Story

Larry Tesler, a computer scientist who worked at Xerox PARC and Apple, developed this principle in the 1980s while working on personal computer interfaces. He observed that simplifying the user's experience of a task always required more complexity somewhere in the system — more engineering work, more edge case handling, more intelligent defaults. The complexity doesn't disappear; it relocates. Tesler reportedly wore a T-shirt that read "No Modes" as a statement on unnecessary complexity in UI.

---

## Why It Matters for the Design OS

1. **"Make it simpler" always has a cost.** When a PM or stakeholder asks to simplify a flow, the question is not whether it can be done, but where the complexity will land. Engineering effort? Configuration complexity? Help center burden? Be explicit about the trade-off.
2. **There's a floor.** Some tasks are genuinely complex. A tax filing tool, a medical records system, an enterprise configuration screen — these have irreducible complexity. Pretending otherwise by hiding it doesn't make the experience better; it makes it confusing.
3. **Defaults absorb complexity.** One of the best ways to shift complexity away from users is to replace decisions with intelligent defaults. The system carries the complexity; users experience simplicity.

---

## Implementation Guidelines

| Strategy | Application |
| :--- | :--- |
| **Use smart defaults aggressively** | Every configuration decision you make on behalf of users via defaults removes one instance of complexity from their path. |
| **Progressive disclosure** | Show simple first; reveal complexity only when users need it. Complexity isn't eliminated — it's deferred until the moment it's needed. |
| **Push complexity to setup, not to use** | If a feature requires configuration, front-load it during setup rather than surfacing it mid-task. |
| **Be honest about irreducible complexity** | Don't oversimplify a genuinely complex domain to the point where users can't accomplish real tasks. The simplest version of a broken workflow is still broken. |
| **Automate what you can** | Engineering complexity (parsing, formatting, intelligent defaults) is far cheaper to the user than interaction complexity. Trade one for the other where possible. |

---

## Tesler's Law vs. Occam's Razor

These principles are often confused but serve different purposes:
- **Occam's Razor** says: don't add complexity that doesn't need to exist. Eliminate unnecessary features and interactions.
- **Tesler's Law** says: for the complexity that *must* exist, decide where it lives. It will end up somewhere.

A good design process applies both: first remove unnecessary complexity (Occam's Razor), then deliberately place the remaining necessary complexity where it causes the least user harm (Tesler's Law).

> **The Design OS Motto:** *You can't make it simpler. You can only make it someone else's problem — choose wisely.*

---

## Related Principles

- **Occam's Razor:** Partner principle — remove avoidable complexity before applying Tesler's Law to what remains.
- **Progressive Disclosure:** The primary UX pattern for applying Tesler's Law — defer complexity until needed.
- **Cognitive Load:** Tesler's Law is about managing where cognitive load lands, not eliminating it.
- **Paradox of the Active User:** Users won't read documentation that holds the shifted complexity. Don't put it there.

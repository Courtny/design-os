# Context File: Doherty Threshold

**Status:** Core Interaction Principle  
**Tagline:** "Waiting breaks the spell."

---

## Executive Summary

The **Doherty Threshold** states that productivity and engagement soar when a system responds to user input in under 400 milliseconds. Once response time exceeds this threshold, the user's attention begins to drift, the sense of flow breaks, and the interaction starts to feel like a tool rather than an extension of thought. Speed is not a feature — it's the baseline requirement for a satisfying experience.

---

## The Origin Story

Walter J. Doherty and Ahrvind J. Thadani published research at IBM in 1982 showing that response times under 400ms dramatically increased user productivity and satisfaction. The key insight was not just that fast is better, but that there is a specific *threshold* — below it, the human-computer interaction feels like a continuous loop; above it, the loop breaks.

---

## Why It Matters for the Design OS

1. **Latency is a UX problem, not just an engineering problem.** If a component or interaction exceeds 400ms, it needs either performance work or a perceived-performance solution (skeleton screens, optimistic UI, progress indicators).
2. **Perceived performance often matters more than actual performance.** A 600ms operation with a skeleton screen and smooth transition feels faster than a 300ms operation with a spinner and jarring content swap.
3. **The threshold applies to micro-interactions too.** Button feedback, hover states, dropdown animations — if they lag, they break the sense of direct manipulation.

---

## Implementation Guidelines

| Target | Threshold | Strategy |
| :--- | :--- | :--- |
| **Instant feedback** | < 100ms | Button press states, hover effects, input focus — should feel immediate. Anything here that lags is noticeable. |
| **Flow-preserving** | 100ms–400ms | Page transitions, search results, filter updates. Use optimistic UI and animate in this range. |
| **Loader required** | 400ms–1000ms | A visible progress indicator is required. Skeleton screens preferred over spinners. |
| **Progress communication** | > 1000ms | Show percent completion or a step indicator. Give users something to track. |

### Perceived Performance Techniques
- **Skeleton screens** over spinners — they communicate structure before content
- **Optimistic UI** — update the interface immediately, reconcile with the server in the background
- **Instant feedback** on all interactive elements, even if the action isn't complete yet
- **Progressive loading** — show partial content as it arrives rather than waiting for the full payload

---

## The Risk: Fake Fast

Artificially inflating perceived speed (fake progress bars, unnecessary loading animations on things that are already fast) erodes trust when users notice the mismatch. The goal is accurate representation of system state at the fastest possible pace.

> **The Design OS Motto:** *If users are waiting, they're leaving — or losing trust.*

---

## Related Principles

- **Flow:** Sustained flow states depend on sub-400ms response cycles. Latency is one of the main flow-breakers.
- **Affordance:** A button that doesn't respond instantly has a weak affordance — it feels broken.
- **Cognitive Load:** Waiting adds extraneous cognitive load (uncertainty, anxiety about whether the action registered).

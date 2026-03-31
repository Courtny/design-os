# Context File: Zeigarnik Effect

**Status:** Core Interaction Principle  
**Tagline:** "Incomplete tasks stay in your head. Completed ones don't."

---

## Executive Summary

The **Zeigarnik Effect** is the tendency for people to remember uncompleted or interrupted tasks better than completed ones. When a task is left open, the brain maintains a low-level background process — a kind of mental "open tab" — that keeps it accessible. This makes unfinished tasks cognitively present in a way that finished tasks aren't. For designers, this is both a user engagement mechanism (incomplete flows pull users back) and a cognitive burden to manage (too many open loops creates anxiety and distraction).

---

## The Origin Story

Soviet psychologist Bluma Zeigarnik documented the effect in 1927 after her professor, Kurt Lewin, noticed that waiters could remember unpaid orders in extraordinary detail but forgot the orders entirely once the bill was settled. Zeigarnik ran experiments confirming the pattern: participants recalled twice as many incomplete tasks as completed ones. The incompleteness creates a persistent cognitive "tension" that keeps the task mentally available.

---

## Why It Matters for the Design OS

1. **Incomplete flows drive re-engagement.** An abandoned checkout, an unfinished profile, a half-completed onboarding — these create genuine psychological pull for users. Re-engagement emails referencing incomplete tasks have higher open rates because the tension is already there.
2. **Progress indicators create open loops.** Showing a user they're "60% complete" doesn't just inform them — it activates the Zeigarnik Effect. The incomplete state creates a pull toward finishing.
3. **Too many open loops creates cognitive overload.** Users with dozens of notifications, incomplete tasks, and unresolved states experience the Zeigarnik Effect as anxiety rather than engagement. Good design resolves open loops rather than accumulating them.

---

## Implementation Guidelines

| Pattern | Application |
| :--- | :--- |
| **Profile completion indicators** | "Your profile is 3 steps from complete" activates an incomplete loop. Users are more likely to finish because the open state is mentally uncomfortable. |
| **Re-engagement notifications** | "You left items in your cart" and "You're almost done setting up X" work because the incomplete state already exists in the user's memory. |
| **Progress bars in multi-step flows** | Don't show a blank progress bar at the start. Start users at step 1 of N from the first screen so the loop opens immediately. |
| **Save draft functionality** | When users can see their in-progress work persisted, the open loop creates a strong pull to return and complete it. |
| **Don't over-accumulate loops** | Notification counts, badge numbers, and unresolved states all create open Zeigarnik loops. When they pile up, they create anxiety rather than motivation. Provide clear ways to resolve or dismiss. |

---

## Zeigarnik Effect and Goal-Gradient

The two principles reinforce each other:
- **Zeigarnik** pulls users back to incomplete tasks because the open state is cognitively uncomfortable
- **Goal-Gradient** pushes users to complete tasks faster as they get closer to the finish line

Together, they create a powerful completion funnel: the open loop pulls users to return; the visible proximity to completion pushes them through to the end.

> **The Design OS Motto:** *An unfinished task is a door left open. Design the pull toward closing it.*

---

## Related Principles

- **Goal-Gradient Effect:** The closer a user is to finishing, the stronger the pull — Zeigarnik provides the initial pull to start.
- **Working Memory:** Open loops occupy working memory; resolving them frees it.
- **Flow:** Persistent incomplete tasks can interfere with flow by occupying background cognitive attention.
- **Selective Attention:** Open Zeigarnik loops can direct attention toward task-related cues in the environment.

# Context File: Working Memory

**Status:** Core Interaction Principle  
**Tagline:** "The screen is smarter than the user's head."

---

## Executive Summary

**Working memory** is the cognitive system that temporarily holds and manipulates information needed to complete a task. It is distinct from long-term memory: working memory is active, limited, and fragile. Designers interact with working memory constantly — every time a user has to remember something from one screen to use it on the next, every time a form requires them to hold context while filling out fields, every time a complex flow requires them to track their own progress. When the interface offloads working memory work onto the user, errors and frustration follow.

---

## Background

Working memory was theorized by Alan Baddeley and Graham Hitch in 1974 as an evolution of the earlier "short-term memory" concept. Their model includes a central executive (attention control), a phonological loop (verbal/auditory information), and a visuospatial sketchpad (visual/spatial information). Capacity is limited in both quantity (roughly 4 items, per more recent research by Cowan, 2001) and duration (seconds, without active rehearsal).

> See also: [`millers-law.md`](millers-law.md) — Miller's Law describes the capacity constraint; working memory is the underlying system.

---

## Why It Matters for the Design OS

1. **Multi-screen flows require working memory.** When users carry information from step 1 to step 3 in their heads, working memory is taxed. The interface should do that carrying for them: show a summary sidebar, repeat key information at decision points, or persist form values across steps.
2. **Interruptions destroy working memory.** A phone notification, a page redirect, an unexpected modal — any interruption can wipe a user's working memory of the task context they were holding. Design flows to minimize interruption and recover gracefully when it happens.
3. **Working memory is shared across visual and verbal channels.** A complex diagram and a complex label competing for attention on the same screen split working memory across both channels, degrading both. Simplify one or separate them.

---

## Implementation Guidelines

| Strategy | Application |
| :--- | :--- |
| **Persist context across steps** | In multi-step flows, show a summary of what the user has already done. Don't make them remember it. |
| **Repeat critical information at decision points** | If a user needs to know their plan type to choose add-ons, show the plan type on the add-on screen. Don't make them hold it in memory. |
| **Recognition over recall** | Show users their options (recognition) rather than requiring them to remember and type them (recall). Dropdowns, autocomplete, and option lists all offload working memory work. |
| **Don't split related information across screens** | If two pieces of information are needed to make one decision, they belong on the same screen. |
| **Reduce interruptions in task flows** | Avoid non-essential modals, alerts, and redirects mid-task. Each one risks losing the user's working memory state. |

---

## Working Memory vs. Long-Term Memory

Design affects both differently:
- **Working memory** is active during a session — it holds current task context and is depleted by complexity and time
- **Long-term memory** is built over sessions — it holds learned patterns, interface conventions, and product knowledge

Conventions and consistent patterns reduce working memory load by converting what would be active processing into long-term pattern recognition. Familiar UI is easier not because it's simple, but because users don't have to hold it in working memory — they already know it.

> **The Design OS Motto:** *The interface should remember, so users don't have to.*

---

## Related Principles

- **Miller's Law:** The quantitative constraint on working memory capacity; see `millers-law.md`.
- **Chunking:** The primary technique for extending effective working memory through grouping.
- **Cognitive Load:** Working memory capacity is the resource that cognitive load depletes.
- **Selective Attention:** Working memory and attention are tightly coupled — when attention is divided, working memory is split.

# Context File: Cognitive Load

**Status:** Core Interaction Principle  
**Tagline:** "The interface is a conversation with a limited audience."

---

## Executive Summary

**Cognitive load** is the total amount of mental effort a user must expend to understand and interact with an interface. It is finite. When an interface demands too much cognitive work — through visual noise, unclear labeling, inconsistent patterns, or excessive choice — users make more errors, feel frustrated, and abandon tasks. Managing cognitive load is one of the most practical lenses for evaluating any design decision.

---

## The Three Types (John Sweller, 1988)

Cognitive load theory was developed in educational psychology but maps cleanly to UI design:

| Type | Definition | Design Implication |
| :--- | :--- | :--- |
| **Intrinsic Load** | The inherent complexity of the task itself | Can't be eliminated, only structured. Use progressive disclosure to pace it. |
| **Extraneous Load** | Complexity added by poor design or presentation | This is the enemy. Every unnecessary option, unclear label, and inconsistent pattern adds extraneous load. Eliminate it. |
| **Germane Load** | Mental effort spent building useful mental models | Worth supporting. Good information architecture, consistent patterns, and sensible defaults help users build accurate mental models. |

---

## Why It Matters for the Design OS

Every element on screen costs attention. The budget is not infinite — it's actually smaller than most designers assume:
1. **Task completion degrades under load.** The more a user has to think about the interface, the less mental energy they have for their actual goal.
2. **Errors increase with complexity.** Most "user errors" are not user failures — they're signals that the interface exceeded cognitive capacity at that moment.
3. **Aesthetic coherence reduces load.** Consistent, predictable UI patterns reduce cognitive work. Users can operate on pattern-matching (System 1) instead of deliberate reasoning (System 2).

---

## Implementation Guidelines

| Strategy | Application |
| :--- | :--- |
| **Minimize choices at any step** | Each decision point adds load. Use smart defaults and progressive disclosure. |
| **Use familiar patterns** | Deviation from Jakob's Law forces users into System 2 thinking. Use conventions unless you have a strong reason not to. |
| **Chunk and label content** | Group related items and give each group a clear header. Labels reduce the work of categorization. |
| **Eliminate decorative complexity** | Visual noise that doesn't communicate anything is pure extraneous load. Remove it. |
| **Inline help reduces remediation load** | Put contextual guidance where users need it, not in a separate help section they'll never visit. |
| **Preserve recognition over recall** | Show users their options rather than requiring them to remember them. |

---

## How to Spot High Cognitive Load in a Design

- Users frequently pause or re-read instructions
- Error rates spike at a specific step
- Users ask "what does this mean?" about UI labels
- User testing sessions show hesitation at decision points
- Completion rates drop mid-funnel without an obvious cause

---

## Related Principles

- **Miller's Law / Working Memory:** Cognitive load theory's root; limited working memory is why load matters.
- **Chunking:** The primary technique for managing intrinsic load.
- **Hick's Law:** More choices = higher cognitive load at decision points.
- **Progressive Disclosure:** The structural pattern for pacing cognitive load over time.
- **Gestalt Principles:** Visual grouping reduces extraneous load by making structure perceivable.

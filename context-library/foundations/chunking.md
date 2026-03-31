# Context File: Chunking

**Status:** Core Interaction Principle  
**Tagline:** "Break it up so the brain can keep up."

---

## Executive Summary

**Chunking** is the process of breaking individual pieces of information into grouped, meaningful units. The brain is much better at processing and remembering a few organized groups than a long list of isolated items. In UI design, chunking is the practical application of Miller's Law: we don't just limit the number of things on screen, we organize them so they're easier to perceive and act on.

---

## The Origin Story

George Miller's 1956 paper "The Magical Number Seven, Plus or Minus Two" established that working memory can hold roughly 7 items at once. But the key insight, often overlooked, was that those "items" could themselves be chunks — compressed packages of multiple pieces of information. A phone number like 4155551234 is hard to recall; (415) 555-1234 is easy, because chunking groups the digits into units the brain already recognizes.

---

## Why It Matters for the Design OS

1. **Chunking reduces perceived complexity.** A form with 20 fields feels daunting. The same form split into four labeled sections of 5 fields each feels manageable.
2. **Visual grouping communicates structure.** When elements are visually chunked, users understand hierarchy and relationships without reading labels.
3. **Chunked content is scannable.** Users rarely read interfaces — they scan. Chunking creates the anchor points their eyes jump between.

---

## Implementation Guidelines

| Pattern | Application |
| :--- | :--- |
| **Group related fields in forms** | Separate personal info, contact details, and payment into distinct sections. Label each group clearly. |
| **Use white space as a divider** | Consistent spacing between chunks communicates separation without lines or borders. |
| **Limit list items per group** | Aim for 3–7 items per visual group before breaking into a new section or adding a "show more." |
| **Apply to navigation** | Group nav items by task type or frequency, not alphabetically. Users chunk by mental model, not alphabetical order. |
| **Use cards to wrap content** | Cards are the most literal implementation of chunking in UI — one coherent unit of content per container. |

---

## Chunking vs. Information Architecture

Chunking is a perceptual strategy; IA is structural. Chunking informs how information is *displayed*; IA informs how it's *organized*. Good design does both: the IA creates the right groupings, and chunking makes those groupings visually obvious.

---

## Related Principles

- **Miller's Law:** Chunking is the technique; Miller's Law is the cognitive constraint it addresses.
- **Law of Proximity:** Objects placed near each other are perceived as a group — the visual mechanism that makes chunking work.
- **Law of Common Region:** Enclosing elements in a bounded area creates a strong chunk.
- **Working Memory:** Chunking extends the effective capacity of working memory by compressing information.

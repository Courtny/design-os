# Context File: Postel's Law

**Status:** Core Interaction Principle  
**Tagline:** "Be flexible in what you accept. Be precise in what you send."

---

## Executive Summary

**Postel's Law** (also called the Robustness Principle) states: *be liberal in what you accept, and conservative in what you send*. Originally an engineering principle for network protocols, it translates directly to UX: design forms and inputs that accept a wide variety of user input formats without breaking, while ensuring the system outputs clean, consistent, predictable responses. Don't punish users for formatting. Do the formatting work for them.

---

## The Origin Story

Jon Postel wrote the Robustness Principle into RFC 761 (TCP specification) in 1980: "Be conservative in what you do, be liberal in what you accept from others." His intent was to make network protocols resilient — a strict sender and a tolerant receiver ensures communication even across imperfect implementations. Designers recognized that the principle applied equally well to human-computer interaction, where "imperfect implementations" are just users being human.

---

## Why It Matters for the Design OS

1. **Users don't format data the way systems want — and they shouldn't have to.** Phone numbers with or without dashes, dates in any reasonable format, email addresses with or without capitalization: the system should handle the variance, not the user.
2. **Validation errors are failures of the interface, not the user.** When a form rejects "4155551234" and demands "(415) 555-1234", the error is not the user's fault. Postel's Law says: accept the first format and normalize it.
3. **Trust is built by tolerating imperfection.** An interface that gracefully accepts messy input and produces clean output feels intelligent and trustworthy. An interface that forces perfect input feels brittle and hostile.

---

## Implementation Guidelines

| Input Type | Apply Postel's Law By |
| :--- | :--- |
| **Phone numbers** | Accept any digit string with or without formatting characters (spaces, dashes, parens). Format it on display. |
| **Dates** | Accept multiple date formats (MM/DD/YYYY, YYYY-MM-DD, "March 31", "3/31"). Parse and normalize on submission. |
| **Email addresses** | Accept any case variation. Normalize to lowercase. |
| **Names** | Don't enforce capitalization or split first/last name unless genuinely necessary. |
| **Search queries** | Be tolerant of typos, extra spaces, and case variation. Fuzzy matching and spell correction are implementations of Postel's Law. |
| **File uploads** | Accept the common variants of a format. If you need PNG, also accept JPEG and convert server-side. Don't reject because of file type when conversion is trivial. |

---

## The Caution: "Liberal in what you accept" has limits

Postel's Law was later critiqued (by Mark Nottingham and others) for enabling security vulnerabilities and protocol ambiguity when applied too broadly. In UX terms, the caution is: don't accept ambiguous input if it genuinely changes what the user is asking for. Being liberal means tolerating formatting variance, not ignoring meaningful input differences. Validate for correctness (is this a real email?), not for formatting preference (is this email lowercase?).

> **The Design OS Motto:** *Let users be human. Do the cleanup yourself.*

---

## Related Principles

- **Affordance:** Forms that apply Postel's Law have stronger affordances — they accept what users naturally provide.
- **Paradox of the Active User:** Users won't read format instructions. Postel's Law removes the need for them.
- **Cognitive Load:** Every format requirement adds extraneous cognitive load. Postel's Law eliminates that category of load.
- **Error Prevention (Nielsen's Heuristic #5):** Accepting flexible input is proactive error prevention at the input layer.

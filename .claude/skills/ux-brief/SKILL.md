---
name: ux-brief
description: Create a design brief from a problem statement, PRD, or feature idea. Produces a grounded brief tied to your product context, design system, and research.
version: 1.0
user-invocable: true
---

# `/ux-brief` - UX Brief Creation

Turn a problem statement, feature idea, or PM request into a structured design brief.

## Quick Start

```
/ux-brief                                 → Guided questions to build a brief from scratch
/ux-brief [describe the problem]          → Skip questions you've already answered
/ux-brief [paste a PRD or feature spec]   → I'll extract brief-worthy context from it
```

**Output:** Brief saved to `outputs/briefs/[feature-name]-brief.md`
**Template:** Based on `templates/ux-brief-template.md`
**Time:** 10–20 minutes for the first draft

---

## Context Routing (Internal)

Before drafting, check:

| Source | Files/Folders | What to extract |
|--------|---------------|-----------------|
| Product context | `context-library/product-context-template.md` | Users, platforms, business goals, design constraints |
| Research | `context-library/research/` | Existing evidence for the problem, user quotes |
| Design system | `context-library/design-system/principles.md` | Principles that apply to this problem |
| Past decisions | `context-library/decisions/` | Decisions that constrain the solution space |
| Related specs | `context-library/design-specs/` | Prior work on adjacent problems |
| Storybook | `context-library/design-system/storybook.md` | Components that likely apply |
| Figma MCP (if connected) | Current design files | Existing flows or explorations for this area |

---

## Guided Questions

When starting from scratch, ask these in sequence. Don't ask all at once — start with 1–2, then follow up.

**Round 1 (required):**
1. "What problem are we solving? Who has it, and in what situation?"
2. "What's the evidence — research, analytics, support tickets, direct quotes?"

**Round 2 (scoping):**
3. "What does success look like? How would you know it worked?"
4. "What's in and out of scope for this version?"

**Round 3 (constraints):**
5. "Any platform, timeline, component, or engineering constraints?"
6. "Who are the key stakeholders and what do they need?"

---

## What to Generate

A complete brief includes:

1. **Problem** — user, situation, pain, evidence
2. **Hypothesis** — If we [do X], then [Y happens] because [Z]
3. **Success criteria** — measurable, tied to user outcomes
4. **Scope** — in v1 / out of v1 (explicit)
5. **Constraints** — platform, component, accessibility, timeline
6. **User journey context** — what happens before and after this moment
7. **Open design questions** — what needs to be resolved during design
8. **Stakeholders** — who reviews what
9. **References** — research links, Figma links, related specs

---

## How to Write It

**Lead with the user's problem, not the solution.** A brief that says "add a filter" is a solution, not a problem. A brief that says "operations managers lose 20 minutes a day hunting through unfiltered event logs" is a problem.

**Be specific.** Quote research. Use real numbers. "47% of sessions end without completing step 3" is better than "users struggle with the flow."

**Scope aggressively.** An explicit "out of scope" section prevents scope creep during design and review. Name things you've decided NOT to do.

**Constraints upfront.** If it must use existing Storybook components, say so in the brief. If it's mobile-only, say so. Engineers and reviewers shouldn't discover constraints in the spec.

---

## Quality Check Before Saving

Before writing the output file, verify:

- [ ] Problem is stated from the user's perspective (not the feature's)
- [ ] Evidence is specific (quotes, numbers, or named research files)
- [ ] Success criteria are measurable (not "improve usability")
- [ ] At least 2–3 things are explicitly called out as out of scope
- [ ] Platform and component constraints are named
- [ ] At least one open design question is identified

---

## Output Quality Self-Check

After generating the brief, scan for:
- Any use of "leverage," "streamline," "robust," "cutting-edge" → remove
- Any em dashes → replace with comma or period
- Any "it was decided" passive voice → make it active
- Any metric that's vague ("improve," "better") → make specific or remove
- Any assumption stated as fact → qualify it

---

## Example Output

```
# UX Brief: Exception Alert Filtering

Author: [designer]
Date: 2026-03-31
Status: Draft

## Problem

Operations managers reviewing daily exception reports spend an average of 18 minutes 
searching through unfiltered event logs to find the items they need to act on.

User: Fleet ops manager at mid-market logistics company
Situation: Morning review of overnight exception reports (happens daily, first 30 min of day)
Pain: No filtering means scrolling through 200+ events to find the 8-12 that need action today
Evidence: Usability study 2025-11 (3/5 participants mentioned filtering unprompted); 
          support tickets: 14 in Q4 related to "can't find my items"

## Hypothesis

If we add rule-based filtering to the exception log, ops managers will spend under 
5 minutes reviewing their daily exceptions because they can surface only their 
priority queue without manual scanning.
...
```

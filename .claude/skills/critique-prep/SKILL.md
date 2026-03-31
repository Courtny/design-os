---
name: critique-prep
description: Prepare a design critique agenda with structured feedback prompts. Grounded in your brief, design system principles, and past critique patterns.
version: 1.0
user-invocable: true
---

# `/critique-prep` - Design Critique Preparation

Build a sharp critique agenda so the session produces decisions, not just opinions.

## Quick Start

```
/critique-prep                              → Guided questions to build agenda from scratch
/critique-prep [describe what you're showing]  → I'll draft the agenda from your description
/critique-prep [paste brief or spec link]   → I'll build from the brief context
```

**Output:** Critique agenda saved to `outputs/critique-notes/[feature]-critique-[date].md`
**Template:** Based on `templates/critique-agenda-template.md`
**Time:** 5–10 minutes

---

## Context Routing (Internal)

Before building the agenda, check:

| Source | Files/Folders | What to extract |
|--------|---------------|-----------------|
| Brief | `outputs/briefs/` or `context-library/design-specs/` | Success criteria, scope, open questions |
| Principles | `context-library/design-system/principles.md` | Which principles apply to this work |
| Component guidance | `context-library/design-system/component-ux/` | Specific component rules to check against |
| Research | `context-library/research/` | Known user expectations or pain points |
| Past critiques | `context-library/meetings/` | What feedback patterns have come up before |
| Figma MCP (if connected) | Linked design file | Current state of work being reviewed |

---

## Guided Questions

1. "What are you showing in this critique?"
2. "What specific decisions do you need feedback to make?"
3. "What's already been decided — what's not up for debate?"
4. "Who's in the room and what's their context?" (designers, PMs, engineers, execs)
5. "How long is the session?"

---

## What Makes a Good Critique Agenda

### Clear goal (not "get feedback")

Bad: "Get feedback on the filter design"
Good: "Decide between Option A (inline filter) and Option B (filter drawer) before moving to hi-fi"

### Explicit "what's decided" section

Tell reviewers what's already resolved. This prevents re-litigating past decisions and focuses energy on what's actually open.

### Specific feedback prompts

Generic: "What do you think?"
Specific:
- "Does this flow match how ops managers describe their morning review process from the November research?"
- "Is the 'save filter' action discoverable enough in Option A, or does it need more prominence?"
- "Which variant better handles the case of 10+ active filters?"

### Audience-aware framing

Adjust what you ask based on who's in the room:
- **Engineers:** Feasibility and implementation risk
- **PMs:** Does this solve the right problem? Does it fit scope?
- **Other designers:** Craft, patterns, consistency with design system
- **Execs:** Strategic fit, user impact, business alignment

---

## Agenda Structure to Generate

1. **Goal** (1–2 sentences: what decisions need to be made today)
2. **Context** (5 min: brief reminder of problem, scope, what's already decided)
3. **Review** (table: each section with time box and focus area)
4. **Feedback prompts** (specific questions per section)
5. **Decisions table** (blank, to fill during session)
6. **Action items table** (blank, to fill during session)
7. **Next steps**

---

## Feedback Prompt Templates

Use these to generate sharp questions. Customize to the work being reviewed.

**For validating problem fit:**
"Does this design address the problem in the brief? What's missing?"

**For pattern consistency:**
"Is this pattern consistent with [related component or area]? Would a user expect this behavior from how [similar feature] works?"

**For accessibility:**
"Can a keyboard-only user complete this flow? Is the focus order logical?"

**For scope:**
"Is anything here out of scope for v1 as stated in the brief? What can we cut?"

**For a specific open question (from the brief):**
"The brief had an open question about [X]. Does what you're seeing resolve it, or does it surface more questions?"

**For choosing between options:**
"Given our principle of [X], which option better supports that? Why?"

---

## Post-Critique Output

After the critique runs, use `/meeting-notes` to process the notes into:
- Decisions made (with rationale)
- Action items (with owners and dates)
- Remaining open questions

If a significant design decision was made, log it using `templates/decision-log-template.md` and save to `context-library/decisions/`.

---

## Quality Check Before Saving

- [ ] Goal is a decision or outcome, not just "get feedback"
- [ ] "Already decided" items are explicitly called out
- [ ] At least 3 specific feedback prompts (not generic "what do you think")
- [ ] Time boxes add up to the session length
- [ ] Decisions and action item tables are blank and ready to fill

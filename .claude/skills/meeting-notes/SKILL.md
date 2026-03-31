---
name: meeting-notes
description: Turn raw critique notes, design sync transcripts, or rough notes into structured meeting summaries with decisions, action items, and open questions.
version: 1.0
user-invocable: true
---

# `/meeting-notes` - Design Meeting Notes

Process raw notes from critiques, design syncs, and stakeholder reviews into clean summaries.

## Quick Start

```
/meeting-notes                              → I'll ask for the notes and context
/meeting-notes [paste raw notes]            → I'll structure them directly
/meeting-notes --critique                   → Critique-specific format (decisions + next steps)
/meeting-notes --sync                       → Design sync format (updates + blockers)
```

**Output:** Notes saved to `outputs/meeting-notes/[meeting-type]-[date].md`
**Time:** 5–10 minutes

---

## Context Routing (Internal)

Before processing, check:

| Source | Files/Folders | What to extract |
|--------|---------------|-----------------|
| Critique agenda | `outputs/critique-notes/` | Goals and open questions the critique was meant to resolve |
| Brief or spec | `outputs/briefs/`, `outputs/design-specs/` | Scope and decisions that frame the meeting |
| Stakeholder profiles | `context-library/stakeholder-template.md` | Communication style, what to watch for |
| Past meeting notes | `context-library/meetings/` | Running decisions and prior context |

---

## Meeting Types

### Critique Notes

Focus on: decisions made, feedback given, action items.

Structure:
1. **Goal** (from the agenda — was it achieved?)
2. **What was shown** (one sentence)
3. **Key feedback** (organized by theme, not by person)
4. **Decisions made** (with rationale, not just outcome)
5. **Action items** (owner + due date)
6. **Open questions** (still unresolved, assigned)
7. **Next critique / review**

### Design Sync Notes

Focus on: status updates, blockers, priorities.

Structure:
1. **Date and attendees**
2. **Status updates** (by project or work stream)
3. **Decisions made**
4. **Blockers and dependencies** (with owner)
5. **Action items**
6. **Next sync date**

### Stakeholder Review Notes

Focus on: feedback received, approval status, next steps.

Structure:
1. **What was presented** and to whom
2. **Feedback received** (verbatim quotes where possible)
3. **Decisions or approvals** (explicit "approved" vs "needs revision")
4. **Action items** with owners
5. **Next review** (if needed)

---

## How to Process Raw Notes

1. **Identify the meeting type** and select the right structure
2. **Extract decisions** — separate "we decided X" from "we talked about X"
3. **Formalize action items** — every action needs an owner and a due date. No orphaned todos.
4. **Preserve exact quotes** — especially stakeholder feedback. Quotes are evidence.
5. **Flag open questions** — things discussed but not resolved. Assign an owner to follow up.
6. **Note what to update** — flag if any decisions warrant updating a spec, brief, or decision log

---

## Decisions vs. Discussion

When processing notes, be precise:

**Decision:** The team agreed to do / not do something. Include the rationale.
"Decided: Use inline filter (Option A) over filter drawer. Rationale: keeps the action in context; drawer adds a navigation layer users don't expect."

**Discussion:** Something was raised but not resolved.
"Open: Whether to persist filter state across sessions. [Owner: designer] to check research for evidence before next sync."

**Feedback:** Input from a reviewer that doesn't require a decision yet.
"Feedback from [PM]: concerned that 'Save filter' CTA isn't prominent enough for power users."

---

## Action Item Format

Every action item should have:
- Clear, specific task (not "follow up on filter")
- Owner (specific person, not "team")
- Due date or timeframe

Example:
| Action | Owner | By |
|--------|-------|-----|
| Revise filter panel to increase Save CTA prominence | [Designer] | Friday |
| Check research for evidence on filter persistence | [Designer] | Before next sync |
| Get engineering estimate for FilterDrawer new pattern | [Eng lead] | Next sprint planning |

---

## After Processing

If a significant design decision was made:
- Create a decision log using `templates/decision-log-template.md`
- Save to `outputs/decisions/` (then promote to `context-library/decisions/` when finalized)

If the critique updated the spec:
- Note which file to update
- Prompt the designer: "Want me to update the spec with the decisions from this critique?"

Move processed meeting notes from `outputs/meeting-notes/` to `context-library/meetings/` once reviewed.

---

## Quality Check Before Saving

- [ ] Meeting type and goal stated upfront
- [ ] Decisions have rationale (not just "we decided X")
- [ ] Every action item has an owner and a due date
- [ ] Open questions are assigned to someone for follow-up
- [ ] Direct quotes preserved verbatim (especially stakeholder feedback)
- [ ] Decision log flag added if a significant design decision was made
- [ ] Spec update flag added if the meeting changed the design direction

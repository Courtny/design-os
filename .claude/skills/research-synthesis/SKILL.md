---
name: research-synthesis
description: Turn raw usability session notes, interview transcripts, or evaluation findings into structured insights with themes, quotes, and design implications.
version: 1.0
user-invocable: true
---

# `/research-synthesis` - Design Research Synthesis

Process raw session notes into structured insights that drive design decisions.

## Quick Start

```
/research-synthesis                          → Guided questions to start synthesis
/research-synthesis [paste session notes]    → I'll extract themes and quotes
/research-synthesis [describe the study]     → I'll ask for the raw material
```

**Output:** Synthesis saved to `outputs/research-synthesis/[study-type]-[topic]-[date].md`
**Time:** 15–30 minutes per study

---

## Context Routing (Internal)

Before synthesizing, check:

| Source | Files/Folders | What to extract |
|--------|---------------|-----------------|
| Past research | `context-library/research/` | Prior findings on the same topic — look for patterns or contradictions |
| Current brief | `outputs/briefs/` | What questions this research was meant to answer |
| Past decisions | `context-library/decisions/` | Decisions the research might confirm or challenge |
| Design principles | `context-library/design-system/principles.md` | Principles this research validates or strains |

---

## Guided Questions

1. "What type of research is this? (usability study, discovery interviews, heuristic evaluation, survey, competitive UX, expert review)"
2. "How many sessions/participants?"
3. "What were you trying to learn? (the study goals)"
4. "Paste the raw notes or transcript, or describe the key things you observed."

---

## Synthesis Framework

Process research in this order:

### 1. Extract Observations
Pull specific, factual observations from the raw material:
- What did participants do?
- What did they say (direct quotes)?
- Where did they struggle or succeed?
- What did they expect vs. what happened?

Tag each observation: `[participant #]`, `[task]`, `[observation type: behavior / quote / expectation / error]`

### 2. Identify Themes
Group observations into patterns that cut across multiple participants:
- A theme needs evidence from at least 2–3 participants to be treated as a finding, not an outlier
- Name themes descriptively: "Users expect filter state to persist across sessions" not "filters"
- Note the strength of each theme: strong (4–5/5 participants), moderate (2–3/5), weak (1–2/5)

### 3. Write Findings
For each theme:
- **Headline:** One sentence stating the finding
- **Evidence:** 2–3 supporting quotes or observations
- **Frequency:** How many participants showed this? (X out of Y)
- **Severity (usability studies):** Critical / Serious / Minor
- **Design implication:** What should change, and where?

### 4. Surface Open Questions
What questions did the research raise that it didn't answer?
What would you test next?

### 5. Update Context Files
Flag any findings that should update:
- `context-library/design-system/component-ux/` (evidence changes a component rule)
- `context-library/decisions/` (finding overturns or confirms a design decision)
- `context-library/design-system/principles.md` (finding reveals a gap in principles)

---

## Severity Rating (Usability Studies)

| Severity | Meaning |
|----------|---------|
| Critical | Users cannot complete the task. Blocking. Fix before launch. |
| Serious | Users struggle significantly. 50%+ affected. Fix in this release. |
| Minor | Confusion or hesitation, but task completed. Fix in next iteration. |
| Enhancement | Opportunity to improve satisfaction. Backlog. |

---

## Output Structure

```markdown
# Research Synthesis: [Study Type] — [Topic]

Date: [date]
Study type: [moderated usability / unmoderated / discovery / heuristic / competitive]
Participants: [#]
Sessions: [#]
Study goals: [bullet list]

---

## Key Findings

### Finding 1: [Headline]
Strength: Strong (4/5 participants)
Severity: Serious

**Evidence:**
- "[Quote from P2: exact words]"
- "[Quote from P4: exact words]"
- P3 attempted to [observed behavior] three times before giving up.

**Design implication:**
[Specific, actionable change. Reference components or flows.]

---

### Finding 2: [Headline]
...

---

## Bright Spots

What worked well that we should preserve or expand?

---

## Open Questions

Questions this research raised but did not answer:
1.
2.

---

## Recommended Next Steps

What to do with these findings:
- [Immediate design change]: [where / what]
- [Next research question]: [study type / method]
- [Context library update]: [which file to update]
```

---

## Quote Formatting Rules

- Use exact words from participants — never paraphrase a direct quote
- Tag participant: `"[exact quote]" — P3, Task 2`
- Anonymize if the research was done under NDA: `"[quote]" — Participant 3`
- Include context when needed: `"[quote]" — P1, after viewing the filter panel for the first time`

---

## Quality Check Before Saving

- [ ] Findings have evidence from at least 2 participants (or outliers flagged as such)
- [ ] All direct quotes are verbatim (not paraphrased)
- [ ] Severity ratings present for usability findings
- [ ] Design implications are specific (named components, screens, or flows)
- [ ] "Bright spots" section present — not all feedback is problems
- [ ] Open questions identified for follow-up research
- [ ] Context library update flags noted where relevant

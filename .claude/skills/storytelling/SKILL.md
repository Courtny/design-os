---
name: storytelling
description: |
  Build or critique narratives using Storyteller Tactics (Pip Decks). Use when pitching ideas, structuring presentations, framing research share-outs, selling design decisions, motivating teams, or sharpening any story-shaped argument.
version: 1.0
user-invocable: true
---

# `/storytelling` - Narrative Build and Critique

Apply Storyteller Tactics to design clear, memorable narratives. For in-product microcopy, use `/content-review`. For chart honesty and density, use `/tufte-viz`. For UI layout critique, use `/visual-critique`.

## Quick Start

```
/storytelling                                      → Guided questions, then build or critique
/storytelling [paste draft pitch or outline]       → Critique / reshape an existing narrative
/storytelling [describe the idea and audience]     → Build a story from scratch
/storytelling [goal: convince|sell|lead|…]         → Jump straight to a Recipe
```

**Output (build):** `outputs/briefs/[topic]-story-[date].md`  
**Output (critique):** `outputs/critique-notes/[topic]-story-critique-[date].md`  
**Time:** 10–25 minutes depending on scope  
**Dependencies:** None. Grounded in `context-library/foundations/storyteller-tactics/`.

---

## Context Routing (Internal)

Before building or critiquing, check:

| Source | Files/Folders | What to extract |
|--------|---------------|-----------------|
| Storyteller index | `context-library/foundations/storyteller-tactics/README.md` | Categories, recipes, Desert Island seven, Story Building System |
| Story Building System | `…/story-building-system.md` | Decision flowchart through Concept → Organise |
| Product context | `context-library/product-context-template.md` | Users, constraints, business stakes for the story |
| Stakeholders | `context-library/stakeholder-template.md` | Audience profile inputs |
| Writing styles | `context-library/writing-style-*.md` | Voice once structure is set (exec, engineering, user-facing, internal) |
| Research | `context-library/research/` | Quotes and proof for Explore tactics |
| Brief or draft | Chat, `outputs/briefs/`, or pasted outline | Existing narrative to reshape |

**Always open `storyteller-tactics/README.md` first.** Then either:

1. **Goal is clear** → Open the matching Recipe (`stories-that-convince`, `-sell`, `-lead`, `-motivate`, `-explain`, `-impress`, `-connect`) and read the ingredient cards it names.
2. **Goal is fuzzy** → Walk the Story Building System decision path. Read only the cards needed for the weak step.
3. **Designer wants a fast path** → Start with the Desert Island seven from the README.

Do not invent tactics that aren't in the deck. Cite card titles and filenames when you recommend a pattern.

---

## Guided Questions

Ask these if the designer hasn't given context:

1. "What's the story for? (Pitch, critique, launch note, research share-out, team motivation, customer narrative)"
2. "Who's the audience, and what do you need them to do afterward?"
3. "What's the goal? (Connect, convince, explain, impress, lead, motivate, sell)"
4. "Building from scratch, or critiquing a draft?"
5. "Anything you refuse to claim, or any proof you must include? (Research quotes, metrics, constraints)"

---

## Workflow: Build a Story

### 1. Lock the job of the story

Map the ask to a Recipe when possible:

| Goal | Recipe |
|------|--------|
| Get closer / align | Stories that Connect |
| Explain expertise / win judgment | Stories that Convince |
| Clarify goals | Stories that Explain |
| Nail a presentation | Stories that Impress |
| Show the way | Stories that Lead |
| Make people act | Stories that Motivate |
| Show value | Stories that Sell |

If none fit, run the Story Building System checklist (why → find → role → function → plan → tell → share).

### 2. Choose structure and character

- Prefer one Structure card (often Man in a Hole, Five Ts, or Voyage & Return) unless the audience needs a specific arc (e.g. Innovation Curve for doubters).
- Set Hero & Guide or Trust Me, I'm an Expert so the audience knows who to root for and who to trust.
- Use Audience Profile (and Big, Small, Inside, Outside) so scale and intimacy match the room.

### 3. Add Explore and Style that earn attention

- Explore: Story Listening, That's Funny, Data Detectives, Social Proof, Thoughtful Failures as needed for proof.
- Style: Movie Time, Story Hooks, Three is the Magic Number, Leave it Out, Rolls Royce Moment, Show & Tell.
- Cut abstract claims that don't trigger a mental "movie."

### 4. Draft the narrative

Produce a short, tellable draft (not a deck dump):

- One-sentence stakes
- Beginning / middle / end (or Before / After)
- Turning points and teachable moment if using Five Ts
- Suggested opener hook and closing ask

### 5. Note the Story Bank metadata

Flag what to store later: sources, permissions, when not to tell this story.

---

## Workflow: Critique a Narrative

Work through each area. Only include findings where there's something worth saying.

### 1. Purpose and audience

- Is the job of the story clear? (Which Recipe would this be?)
- Does Audience Profile fit? Wrong intimacy (Big vs Small, Inside vs Outside)?

### 2. Character and trust

- Is the teller the hero when they should be the Guide?
- Is expertise shown with Trust Me, I'm an Expert, or only asserted?
- Does Cut to the Chase / What's it About? apply? Are we burying the point?

### 3. Structure

- Is there a timeline with turning points, or a flat fact list?
- Does Man in a Hole (or another Structure) sharpen the lesson?
- Is the ending a Happy Ever After, a teachable moment, or a shrug?

### 4. Proof and explore

- Are insights from Story Listening or research visible?
- Is data told as Data Detectives, or dumped as a spreadsheet vibe?
- Social Proof: claimed, or shown?

### 5. Style and memory

- Movie Time: can the audience see a scene?
- Three is the Magic Number: too many points?
- Hooks and Leave it Out: dull open, or over-explained close?

### 6. Suggest improvements

For each issue: name the tactic card, say what to change, and sketch a tighter line where helpful.

---

## Quick Checklist

- [ ] Job of the story mapped to a Recipe or Story Building System step
- [ ] Audience (and ask) explicit
- [ ] Role clear (Hero / Guide / Expert)
- [ ] One primary Structure (not mashups without reason)
- [ ] At least one visual "movie" moment
- [ ] Proof path (Explore) without data dump
- [ ] Close with a teachable moment or clear ask
- [ ] Card titles cited (filenames when recommending next reads)

---

## Output Structure: Build

```markdown
# Story Brief: [Topic]

**Date:** [date]
**Audience:** [who]
**Goal:** [connect / convince / explain / impress / lead / motivate / sell]
**Recipe or path:** [e.g., Stories that Convince / Story Building System]

---

## Stakes (one sentence)

[Why this matters now]

---

## Narrative Draft

**Hook:** […]
**Beginning:** […]
**Middle (turning points):** […]
**End / ask:** […]

---

## Tactics Used

| Stage | Card | File | Why |
|-------|------|------|-----|
| | | | |

---

## Proof to Bring

[Research quotes, metrics, Story Listening notes]

---

## Open Questions

[Gaps before telling]
```

---

## Output Structure: Critique

```markdown
# Story Critique: [Topic]

**Date:** [date]
**Source:** [draft / outline / transcript]
**Mode:** critique

---

## Summary

[2–3 sentences: does the story work? What's the main fix?]

---

## Job of the Story

[Mapped Recipe or missing purpose]

---

## Findings

| # | Issue | Location | Tactic | Recommendation |
|---|-------|----------|--------|----------------|
| 1 | [what's weak] | [where] | [card title] | [specific fix] |

---

## What's Working Well

[Specific moments or tactics to keep]

---

## Suggested Rewrite (optional)

[Shorter draft of the weak section, or full reframe if asked]

---

## Suggested Next Steps

[1–3 actions, e.g., "Swap hero for Guide," "Apply Movie Time to the metric slide," "Run Five Ts for an off-the-cuff version"]
```

---

## Quality Check Before Saving

- [ ] `storyteller-tactics/README.md` read and referenced
- [ ] Recommendations cite real deck cards (no invented tactics)
- [ ] Voice matches audience via the appropriate `writing-style-*.md` when drafting prose
- [ ] Scope stayed on narrative craft (did not duplicate `/content-review` or `/tufte-viz`)
- [ ] Output path correct: briefs for builds, critique-notes for reviews
- [ ] Attribution: Pip Decks cards remain the source; Design OS wrappers don't claim authorship of tactics

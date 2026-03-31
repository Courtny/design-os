# Critique Norms

How we run design critiques on this team. The copilot references this when preparing critique agendas (`/critique-prep`) and processing meeting notes (`/meeting-notes`).

---

## Purpose of Critique

Critique exists to improve the work, not evaluate the designer. The goal is specific, actionable feedback that helps the designer make better decisions before shipping.

Critique is not:
- A design review gate (that's a separate process)
- A brainstorming session (do that before critique)
- A chance to redesign someone's work (offer feedback, not takeovers)

---

## Roles

**Presenter:** The designer showing work. Sets the context, defines what feedback they need, and owns the follow-through.

**Facilitator:** Keeps time, manages the discussion, and makes sure feedback stays on track. Can be the design lead, a rotating peer, or the copilot (via `/critique-prep`).

**Reviewers:** Everyone else. Give feedback on what's presented. Stay within the scope the presenter defines.

---

## Before Critique

The presenter should come prepared with:
- A clear statement of what they're showing and why
- What feedback they need (and what's already decided and not up for debate)
- The relevant Figma file or prototype ready to present
- The brief or spec for reference

Use `/critique-prep` to build the agenda from a brief or spec. It generates structured feedback prompts tied to the specific work.

---

## During Critique

### Structure (45 minutes typical)

| Phase | Time | What happens |
|-------|------|-------------|
| Context | 5 min | Presenter explains the problem, scope, and what they need feedback on |
| Walkthrough | 15-20 min | Walk through the design. Pause after each section for clarifying questions only. |
| Feedback round | 15-20 min | Structured feedback using the prompts below |
| Wrap-up | 5 min | Capture decisions and action items |

### Feedback Prompts

Use these to keep feedback specific and useful:

1. **What's working?** Identify strengths to preserve. Be specific. "The progressive disclosure in the filter panel reduces cognitive load" is better than "looks good."

2. **What's not working or unclear?** State the problem you see, not the solution you'd pick. "I'm confused about which action is primary here" is better than "make that button bigger."

3. **What's missing?** Edge cases, states, or flows the design doesn't address yet.

4. **Open questions:** Things that need answers from PM, engineering, research, or another team.

### Feedback Rules

- **Describe the problem, not the solution.** "The hierarchy isn't clear between these two sections" lets the designer solve it. "Add a divider here" skips the thinking.
- **Be specific.** "This feels off" is not feedback. "The spacing between the form section and the CTA makes them feel disconnected" is.
- **Stay in scope.** If the presenter said "I need feedback on the error states," don't critique the navigation model.
- **Separate taste from usability.** "I personally prefer rounded corners" is taste. "The sharp corners on these cards don't match the rest of our system" is a design system consistency issue.
- **One person at a time.** No cross-talk during the feedback round.

---

## After Critique

1. **Facilitator (or copilot) captures:** decisions made, action items with owners, and open questions
2. **Presenter updates:** the spec or Figma file based on feedback
3. **Decision log:** If a significant design direction was decided, log it in `context-library/decisions/`
4. **Follow-up critique:** Schedule one if major changes are needed

Use `/meeting-notes` to turn raw critique notes into structured decisions and action items.

---

## Anti-Patterns

| Anti-pattern | Why it hurts | What to do instead |
|-------------|-------------|-------------------|
| "Looks good to me" with no specifics | Doesn't help. May hide real concerns. | Ask "what specifically is working?" |
| Redesigning in the meeting | Undermines the designer's ownership | Describe the problem, let them solve it |
| Debating decisions already made | Wastes time, erodes trust | Respect the scope the presenter set |
| Only senior people giving feedback | Misses diverse perspectives | Rotate facilitation. Explicitly invite juniors to speak first. |
| No follow-through | Feedback without action is noise | Assign owners and due dates for every action item |

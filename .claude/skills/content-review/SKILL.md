---
name: content-review
description: Review microcopy, labels, error messages, and content hierarchy in a design or spec. Grounded in your writing styles, design principles, and component UX guidance.
version: 1.0
user-invocable: true
---

# `/content-review` - Content and Microcopy Review

Review all visible text in a design for clarity, consistency, and tone. This isn't a copyedit. It's a UX content review: does the text help users understand where they are, what to do, and what happens next?

## Quick Start

```
/content-review                                → Guided questions, then attach or describe the design
/content-review [attach image]                 → Review copy visible in a screenshot or export
/content-review [paste spec]                   → Review all microcopy in a spec
/content-review [describe a flow or screen]    → I'll ask about the copy decisions
```

**Output:** Review saved to `outputs/critique-notes/[feature]-content-review-[date].md`
**Time:** 10–20 minutes
**Dependencies:** None. Better with writing style files filled out.

---

## Context Routing (Internal)

Before reviewing, check:

| Source | Files/Folders | What to extract |
|--------|---------------|-----------------|
| Writing styles | `context-library/writing-style-*.md` | Tone, structure, capitalization, what to avoid |
| Content rules | `context-library/design-system/principles.md` → Content and Microcopy section | Voice, tense, capitalization, error/empty/loading message rules |
| Component UX | `context-library/design-system/component-ux/` | Component-specific copy guidance (e.g., button labels should be verb-led) |
| Product context | `context-library/product-context-template.md` | User type, domain, terminology |
| Research | `context-library/research/` | User language, mental models, terminology confusion |

---

## Guided Questions

Ask these when no context is provided:

1. "What am I looking at? (Screen, flow, component, spec)"
2. "Who's the primary audience? (End users, admins, internal ops)"
3. "Is this first-draft copy or near-final?"
4. "Any specific labels, messages, or sections you're unsure about?"

---

## Review Framework

### 1. Labels and Headings

- Are labels specific? "Email address" beats "Email." "Billing address" beats "Address."
- Do headings tell users where they are in the flow?
- Is capitalization consistent? (Check `principles.md` for the team's convention; sentence case is the most common.)
- Are labels using the user's language, or internal/technical terms? Cross-reference `product-context-template.md` if filled.

### 2. Button and CTA Copy

- Does every button label say what happens? ("Save changes" not "Submit." "Delete account" not "OK.")
- Is the primary CTA clearly the most important action?
- Are destructive actions labeled specifically? ("Delete this project" not "Delete.")
- Check against `component-ux/button.md` if it exists: verb-led, sentence case, one primary per section.

### 3. Helper Text and Descriptions

- Does helper text answer the question "why does this matter?" or "what should I put here?"
- Is it short enough to scan? (One line, two at most.)
- Is it placed where the user needs it (next to the field, not in a tooltip they'll never open)?
- Avoid restating the label: if the label says "Email address," the helper text shouldn't say "Enter your email address."

### 4. Error Messages

Check every error message against the three rules from `principles.md`:

1. **Say what went wrong.** "This email is already associated with an account" not "Invalid input."
2. **Tell the user how to fix it.** "Try signing in instead, or use a different email."
3. **Don't blame the user.** "We couldn't process that" not "You entered an invalid value."

Also check:
- Is the error message specific to the error? (Not a generic "Something went wrong" for every failure.)
- Is the message inline (next to the field) or only at the top of the form?
- Are there any "show error" placeholders without actual copy?

### 5. Empty States

- Does the empty state explain why it's empty? ("No projects yet" is better than a blank screen.)
- Does it give the user a clear next action? ("Create your first project" with a button.)
- Is the tone appropriate? (Encouraging for first-use, neutral for search results.)
- Check against `principles.md` empty state rules.

### 6. Confirmation and Success Messages

- Do success messages confirm what happened? ("Project saved" not just a green checkmark.)
- Are confirmation dialogs specific? ("Delete 'Q1 Report'? This can't be undone." not "Are you sure?")
- Is the next step clear after success? (What does the user do now?)

### 7. Placeholder Text

- Is placeholder text used as a substitute for labels? (It shouldn't be. Placeholders disappear on focus.)
- Are placeholders showing format hints where helpful? ("MM/DD/YYYY" or "jane@example.com")
- Is placeholder text visually distinct from entered text? (Lower contrast, italic, etc.)

### 8. Terminology Consistency

- Is the same concept always called the same thing? ("Project" not sometimes "project" and sometimes "workspace.")
- Are action verbs consistent? ("Save" vs. "Update" vs. "Apply" for the same type of action.)
- Flag any term that changes meaning or name between screens.
- Build a quick term inventory if the flow is complex.

### 9. Reading Level and Clarity

- Is the copy at an 8th-grade reading level? (Check `principles.md` for user-facing content standard.)
- Are there any sentences that need to be read twice to understand?
- Remove jargon, acronyms without explanation, or domain terms that aren't defined.
- Shorter is almost always better. If a sentence has a comma, ask whether it should be two sentences.

### 10. Tone and Voice

- Does the tone match the team's defined voice? (Check `writing-style-*.md` files.)
- Is it consistent across the flow? (Don't be playful on the onboarding screen and clinical on the error screen.)
- Is it appropriate for the context? (Lighter for onboarding, neutral for settings, careful for destructive actions.)
- Flag any text that sounds generated, corporate, or overly formal compared to the team's style.

---

## Output Structure

```markdown
# Content Review: [Screen or Feature Name]

**Date:** [date]
**Source:** [image / spec / description]
**Audience:** [end users / admins / internal]
**Writing style files checked:** [yes / partial / not filled out]

---

## Summary

[2–3 sentences: overall content quality. Is the copy helping users or getting in their way?]

---

## Findings

| # | Location | Current copy | Issue | Suggested revision | Ties to |
|---|----------|-------------|-------|-------------------|---------|
| 1 | [field, button, heading, message] | [exact text] | [what's wrong] | [proposed replacement] | [writing style rule or principle] |

---

## Terminology Inventory

| Term | Used in | Consistent? | Notes |
|------|---------|-------------|-------|
| [term] | [where it appears] | [yes / no] | [conflicting usage if any] |

---

## What's Working Well

[Specific copy decisions to preserve. Good error messages, clear CTAs, etc.]

---

## Missing Copy

[Placeholder text, [TBD] markers, unlabeled icons, missing error or empty states.]

---

## Suggested Next Steps

[1–3 actions. e.g., "Define voice characteristics in principles.md," "Write out all error messages for the form validation flow."]
```

---

## Quality Check Before Saving

- [ ] Writing style files checked (`writing-style-*.md`)
- [ ] `principles.md` Content and Microcopy section checked
- [ ] Every error message evaluated against the three rules (what went wrong, how to fix, don't blame)
- [ ] Every button label checked for specificity (verb + object)
- [ ] Terminology consistency checked across the flow
- [ ] Empty states reviewed for explanation + next action
- [ ] Placeholder text not substituting for labels
- [ ] Findings include specific suggested revisions (not just "make it better")
- [ ] Tone checked against team's voice definition

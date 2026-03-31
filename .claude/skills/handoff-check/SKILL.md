---
name: handoff-check
description: Pre-handoff readiness check for a UX spec. Verifies completeness before engineering picks it up.
version: 1.0
user-invocable: true
---

# `/handoff-check` - Pre-Handoff Readiness Check

Run a completeness check on a UX spec before it goes to engineering. Catches missing states, vague copy, unnamed components, and gaps that would trigger questions during implementation.

## Quick Start

```
/handoff-check                                 → I'll ask which spec to review
/handoff-check [spec file path]                → Review a spec from outputs/design-specs/
/handoff-check [paste spec]                    → Review pasted spec content
```

**Output:** Checklist saved to `outputs/critique-notes/[feature]-handoff-check-[date].md`
**Time:** 10–15 minutes
**Dependencies:** None. Better results when `component-ux/` and `storybook.md` are filled out.

---

## Context Routing (Internal)

Before checking, read:

| Source | Files/Folders | What to extract |
|--------|---------------|-----------------|
| Spec | `outputs/design-specs/` or pasted in chat | The artifact being checked |
| Storybook | `context-library/design-system/storybook.md` | Component names to verify against |
| Component UX | `context-library/design-system/component-ux/` | Required states and accessibility rules per component |
| Example specs | `context-library/example-specs/` | What a complete spec looks like for this team |
| Principles | `context-library/design-system/principles.md` | Accessibility standards, content rules, anti-patterns |

---

## What This Checks

This isn't a design critique. It's a completeness audit. The question isn't "is this good design?" but "can an engineer build this without coming back to ask questions?"

---

## Checklist Framework

### 1. Component Names

- [ ] Every component is named exactly as it appears in Storybook
- [ ] Component names aren't generic ("button," "table," "input") but match the actual library name (`Button`, `DataTable`, `TextInput`)
- [ ] Relevant props and variants are specified (not just the component name)
- [ ] New patterns are explicitly called out as "not in Storybook" with full documentation

If `storybook.md` isn't filled out, flag any component names that sound generic and ask the designer to verify they match the actual library.

### 2. States

For every interactive element, check whether these states are documented:

| State | Present? | Notes |
|-------|----------|-------|
| Default | | |
| Hover | | |
| Focus | | |
| Active/pressed | | |
| Disabled | | What triggers it? |
| Loading | | What does it look like? Does it preserve dimensions? |
| Error | | Full error message written out? |
| Empty | | Message + next action? |

Flag any state that's missing. Use `component-ux/` files to know which states are required for each component type.

### 3. Error Messages

- [ ] Every error message is written out in full (no "show error" or "display validation message")
- [ ] Each message says what went wrong
- [ ] Each message tells the user how to fix it
- [ ] Error placement is specified (inline, toast, banner)
- [ ] Server/network error handling is documented (not just field validation)

### 4. Empty States

- [ ] Every zero-data scenario is accounted for:
  - First use (nothing has been added yet)
  - Search/filter with no results
  - Content that's been deleted or archived
- [ ] Each empty state has explanatory text
- [ ] Each empty state has a clear next action (button or link)
- [ ] The component used for empty states is specified

### 5. Microcopy

- [ ] All headings, labels, and placeholders are written out
- [ ] All button labels are specific (verb + object, not "Submit" or "OK")
- [ ] Helper text is present where users need guidance
- [ ] Confirmation dialog copy is complete
- [ ] Success messages are written out
- [ ] No `[TBD]`, `[copy needed]`, or placeholder markers remain

### 6. Responsive Behavior

- [ ] Breakpoints are defined (or stated as "same across breakpoints")
- [ ] Layout changes at mobile/tablet/desktop are described
- [ ] Touch target sizing is accounted for on mobile (44x44px minimum)
- [ ] Any elements that hide/show at different breakpoints are noted
- [ ] Stack order on mobile is specified for side-by-side layouts

### 7. Accessibility

- [ ] Focus order is described (tab sequence through the flow)
- [ ] Any non-standard keyboard interactions are documented
- [ ] ARIA attributes are noted for custom components
- [ ] Color contrast flags are addressed (or deferred to `/accessibility-review`)
- [ ] Screen reader announcements are specified for dynamic content

### 8. Edge Cases

- [ ] Maximum content lengths are defined (what happens with long names, long emails, overflowing text?)
- [ ] Permission-based visibility is documented (what do different user roles see?)
- [ ] Network failure handling is specified
- [ ] Browser back button behavior is documented for multi-step flows
- [ ] Concurrent editing or race conditions noted where applicable

### 9. Figma/Design File Alignment

- [ ] Spec references specific Figma frames or provides visual mockups
- [ ] Design file and spec are in sync (no outdated screenshots or stale references)
- [ ] Annotations in the design file match what's in the spec

### 10. Out of Scope

- [ ] Out of scope section exists and is explicit
- [ ] It's clear what v1 doesn't include
- [ ] No assumptions about "future work" that might confuse engineering scope

---

## Severity for Missing Items

| Severity | Meaning | Impact on handoff |
|----------|---------|-------------------|
| **Blocker** | Engineer cannot build this section without the missing info. Spec is incomplete. | Must fix before handoff. |
| **Gap** | Engineer would need to ask a clarifying question. Not blocking, but slows velocity. | Fix before handoff if possible. |
| **Nice to have** | Spec works without it, but including it would prevent a question later. | Fix during implementation or next pass. |

---

## Output Structure

```markdown
# Handoff Check: [Feature Name]

**Date:** [date]
**Spec reviewed:** [file path or "pasted in chat"]
**Overall readiness:** [Ready / Almost ready / Not ready]

---

## Summary

[2–3 sentences: is this spec ready for engineering? What's the biggest gap?]

---

## Checklist Results

| Area | Status | Blockers | Gaps | Notes |
|------|--------|----------|------|-------|
| Component names | [pass / issues] | [#] | [#] | |
| States | [pass / issues] | [#] | [#] | |
| Error messages | [pass / issues] | [#] | [#] | |
| Empty states | [pass / issues] | [#] | [#] | |
| Microcopy | [pass / issues] | [#] | [#] | |
| Responsive | [pass / issues] | [#] | [#] | |
| Accessibility | [pass / issues] | [#] | [#] | |
| Edge cases | [pass / issues] | [#] | [#] | |
| Design alignment | [pass / issues] | [#] | [#] | |
| Out of scope | [pass / issues] | [#] | [#] | |

---

## Blockers (must fix before handoff)

| # | Area | What's missing | Why it blocks |
|---|------|----------------|---------------|
| 1 | | | |

---

## Gaps (should fix, but not blocking)

| # | Area | What's missing | Suggestion |
|---|------|----------------|------------|
| 1 | | | |

---

## What's Solid

[Specific sections of the spec that are well-documented and ready.]

---

## Suggested Next Steps

[Ordered list of what to fix, starting with blockers. Link to relevant skills if applicable.]
```

---

## Quality Check Before Saving

- [ ] All 10 checklist areas evaluated
- [ ] Blockers clearly distinguished from gaps
- [ ] Missing items are specific ("error message for invalid email is missing") not vague ("needs more detail")
- [ ] "What's solid" section included (acknowledge what's done well)
- [ ] Overall readiness verdict is honest and justified
- [ ] Suggested next steps are actionable and ordered by priority

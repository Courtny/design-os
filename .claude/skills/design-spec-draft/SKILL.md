---
name: design-spec-draft
description: Draft a UX spec with flows, states, edge cases, and component references. Grounded in your Storybook library, design principles, and UX brief.
version: 1.0
user-invocable: true
---

# `/design-spec-draft` - UX Spec Drafting

Turn a brief, PRD, or feature description into a handoff-ready UX spec.

## Quick Start

```
/design-spec-draft                           → Guided questions to draft from scratch
/design-spec-draft [feature description]     → Skip questions you've already answered
/design-spec-draft [paste brief]             → I'll draft from the brief
```

**Output:** Spec saved to `outputs/design-specs/[feature-name]-spec.md`
**Template:** Based on `templates/design-spec-template.md`
**Time:** 20–40 minutes for first draft

---

## Context Routing (Internal)

Before drafting, check:

| Source | Files/Folders | What to extract |
|--------|---------------|-----------------|
| Brief | `outputs/briefs/` or described in chat | Problem, scope, success criteria, constraints |
| Storybook | `context-library/design-system/storybook.md` | Which components exist and which to use |
| Component UX | `context-library/design-system/component-ux/` | Per-component rules, states, anti-patterns |
| Principles | `context-library/design-system/principles.md` | Accessibility standards, anti-patterns |
| Research | `context-library/research/` | User expectations, known edge cases from sessions |
| Example specs | `context-library/example-specs/` | Format and detail level your team uses |
| Past specs | `context-library/design-specs/` | Prior decisions on adjacent patterns |
| Figma MCP (if connected) | Design file | Current visual state of work |

---

## Guided Questions

Start with these if no brief is provided:

1. "What feature are we speccing? Describe it in a sentence."
2. "What platform(s): web, mobile, or both?"
3. "Do you have a Figma file or brief I should reference?"
4. "Any Storybook components you know will be used?"
5. "What are the main user actions in this flow?"

---

## What a Complete Spec Covers

Every spec needs these sections. Flag missing ones rather than skipping them.

### 1. Components Used
List every Storybook component involved. Match names exactly to Storybook.
- If a pattern doesn't exist in Storybook: call it out explicitly as "new pattern"
- Note key props and variants being used (not just the component name)

### 2. Behavior
For each screen or section:
- What the user sees by default
- What happens when they interact (table: user action → system response)
- State transitions

### 3. States (Never Skip These)
Every interactive element needs all relevant states:
- Default, hover, focus, active, disabled, loading, error, empty
- Include what triggers each state
- Note if Storybook handles a state automatically or if the designer needs to spec it

### 4. Error States
Write every error message out in full. "Show error" is not a spec. Good error messages:
- Say what went wrong
- Tell the user how to fix it
- Don't blame the user

### 5. Empty States
Document every zero-data situation:
- First use (no data has ever been added)
- Search/filter that returns no results
- Content that has been deleted
Use the `EmptyState` component from Storybook. Always include a next action.

### 6. Microcopy
Write all visible text:
- Headings, labels, placeholders, helper text, CTAs
- Success messages, confirmation dialogs
- No `[copy TBD]`. If you don't know the copy, flag it as a decision needed.

### 7. Responsive Behavior
For each breakpoint that applies:
- What changes at mobile vs. tablet vs. desktop
- What stays the same

### 8. Accessibility
- Focus order (describe the tab sequence)
- Any non-standard keyboard interactions
- ARIA notes not handled by existing components
- Color contrast flags if using custom colors

### 9. Out of Scope
Explicitly list what v1 does NOT include. This prevents scope creep.

### 10. Open Questions
List any unresolved items with an owner and due date.

---

## Rules for Spec Language

- Use exact Storybook component names: `DataTable`, not "table" or "grid"
- Reference Storybook story paths: "`FormField > With Error`"
- Write error messages in quotes as they'll actually appear to users
- Use second person present tense: "When the user clicks X, Y happens"
- Reference Figma frames with links when they exist
- Call out when something is a new pattern (not in Storybook) so engineering knows

---

## New Patterns Handling

When the spec requires a pattern that doesn't exist in Storybook:

1. Call it out explicitly in the "Components Used" section: **"New pattern: [name] — does not exist in Storybook. See design notes."**
2. Spec it as thoroughly as you would an existing component (states, accessibility, etc.)
3. Flag it for design system contribution review
4. Note the approximate impact (used in 1 place vs. will appear across 8 surfaces)

---

## Quality Check Before Saving

- [ ] Every component is named exactly as it appears in Storybook
- [ ] All interactive states are documented (default through error)
- [ ] Every error message is written out in full — no "show error"
- [ ] Every empty state has a message AND a next action
- [ ] All microcopy is written out — no `[TBD]` placeholders
- [ ] Responsive behavior documented for each relevant breakpoint
- [ ] Accessibility section is present and specific
- [ ] Out of scope section is explicit
- [ ] New patterns are called out and flagged for design system review

---

## Example Component Reference Block

```markdown
## Components Used

| Component | Storybook Path | Props Used | Notes |
|-----------|---------------|------------|-------|
| `FormField` | Forms > FormField | `label`, `helperText`, `errorMessage`, `isInvalid`, `isRequired` | Wraps all inputs |
| `TextInput` | Forms > TextInput | `placeholder`, `value`, `onChange` | Email field |
| `Button` | Actions > Button | `primary`, `isLoading`, `isDisabled` | Submit CTA |
| `Alert` | Feedback > Alert | `error` | Server error feedback |

**New patterns (not in Storybook):**
- `FilterDrawer` — multi-select filter panel. New pattern needed. Design system contribution required before launch.
```

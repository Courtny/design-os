# Handoff Checklist

What "ready for engineering" means on this team. Use this before marking a spec as complete or a Figma file as "Approved."

The copilot uses this checklist when running `/handoff-check`.

---

## The Standard

A spec is ready for handoff when an engineer can build the feature without asking the designer any questions about behavior, states, or edge cases. Visual questions ("is this 8px or 12px?") should be answerable from Figma Inspect or design tokens.

If the engineer has to Slack you "what happens when X?", the spec wasn't done.

---

## Checklist

### Components and Patterns

- [ ] All Storybook component names are correct and match exactly (PascalCase)
- [ ] All variants and props referenced actually exist in the current Storybook version
- [ ] New patterns (not in Storybook) are explicitly called out with a rationale
- [ ] New patterns have been reviewed by the design system owner

### Behavior

- [ ] Every user action has a defined system response
- [ ] Transition logic between screens/states is documented
- [ ] Conditional visibility rules are explicit ("show X when Y")
- [ ] Navigation and routing behavior is clear (what URL, what back button does)

### States

For every interactive element:
- [ ] Default state
- [ ] Hover state (desktop)
- [ ] Focus state (keyboard navigation)
- [ ] Active/pressed state
- [ ] Disabled state (with explanation of when and why)
- [ ] Loading state (with timing: when does it start, when does it end)
- [ ] Error state (with specific error messages written out)
- [ ] Empty state (with message and next action)
- [ ] Success state (with confirmation message)

### Microcopy

- [ ] All labels, headings, and button text are final (no "[TBD]")
- [ ] All error messages written out with specific, helpful language
- [ ] All empty state messages include a next action
- [ ] All placeholder text is final
- [ ] Confirmation dialogs have final copy for title, body, and both action labels
- [ ] Sentence case used consistently

### Edge Cases

- [ ] Long text / overflow behavior defined (truncation, wrapping, tooltips)
- [ ] Zero items state defined
- [ ] Maximum items or character limits defined
- [ ] Slow network behavior specified (loading, timeout, retry)
- [ ] Concurrent action handling specified (double-submit prevention, optimistic UI)
- [ ] Permission-denied state defined (if applicable)

### Responsive

- [ ] Behavior specified for each relevant breakpoint
- [ ] Touch target sizes meet minimums (44x44px for mobile)
- [ ] Any layout changes between breakpoints are documented
- [ ] Hover-dependent interactions have mobile alternatives

### Accessibility

- [ ] Focus order documented and matches visual reading order
- [ ] Keyboard interactions specified for custom components
- [ ] ARIA attributes noted where components don't handle them automatically
- [ ] Color contrast verified for all custom colors (not just design tokens)
- [ ] Screen reader announcements noted for dynamic content changes
- [ ] `prefers-reduced-motion` considered for any animations

### Figma

- [ ] All frames use Storybook-matched components (or mismatches noted)
- [ ] Annotation layers present for behavior that isn't obvious from the visual
- [ ] Frame labels use status convention: "Approved" for handoff-ready
- [ ] Link to UX spec included in Figma file description or annotation

### Spec Document

- [ ] Overview is one or two sentences (engineer can skim it)
- [ ] Component table is complete
- [ ] Out of scope section is explicit
- [ ] Open questions resolved (or owners assigned with dates)
- [ ] Revision history updated

---

## Common Gaps

These are the things most often missing from specs. Check them twice.

| Gap | Why it matters |
|-----|---------------|
| Loading states | Engineers need to know what's disabled, what shows a spinner, and when the spinner appears |
| Error message copy | "Show an error" is not a spec. Write the actual message. |
| Empty states | Engineers will build a blank screen if you don't spec the empty state |
| Focus order | Screen reader and keyboard users will hit elements in DOM order unless you specify otherwise |
| Long text behavior | If someone pastes a 200-character name, what happens? Truncate? Wrap? Error? |
| Mobile touch alternatives | Hover tooltips don't work on mobile. What replaces them? |

---

## After Handoff

- [ ] Walk through the spec with the implementing engineer (15 min is usually enough)
- [ ] Confirm the engineer has access to the Figma file and Storybook
- [ ] Agree on a check-in point (mid-build review, not just final QA)
- [ ] Spec stays in `outputs/design-specs/` during build, moves to `context-library/design-specs/` after ship

# Writing Style: Engineering Handoff Docs

Use this style for: UX specs, annotation layers, component contribution docs, anything an engineer will build from.

---

## The Job of a Handoff Doc

Engineers shouldn't have to guess. If they're asking "what happens when X?" the spec failed.

## Structure

Every spec should cover:
1. **What this is** — one sentence
2. **Components used** — exact Storybook names and variants
3. **Behavior** — interactions, state transitions
4. **States** — default, hover, focus, active, disabled, loading, empty, error
5. **Edge cases** — long text, missing data, slow network, zero results
6. **Accessibility** — focus order, ARIA roles, keyboard interactions, color contrast
7. **Out of scope** — what we're explicitly not doing in this version

## Language Rules

- Component names match Storybook exactly: `TextInput`, not "input" or "text field."
- Reference Storybook story paths: "`FormField > With Helper Text`"
- Reference Figma frames with direct links when specs are annotated there.
- Use second person when writing behavior: "When the user clicks X, Y happens."
- Use present tense for states: "The button is disabled when the form is empty."
- Use exact copy for all microcopy, labels, placeholders, and error messages. No "TBD."

## Specificity Checklist

Before handing off, confirm:
- [ ] All interactive states documented
- [ ] All error messages written out (not "show error")
- [ ] Empty states defined (zero results, no data, first use)
- [ ] Loading states specified
- [ ] Responsive behavior described for each breakpoint
- [ ] Accessibility requirements listed
- [ ] Known edge cases called out
- [ ] Out of scope stated explicitly

## What to Avoid

- Annotating in Figma but not in the spec doc (engineers shouldn't have to hunt)
- "Looks like X" comparisons without the specific component name
- Leaving placeholders like "[copy TBD]" or "[edge case TBD]"
- Describing behavior in past tense ("it was clicked" vs "when clicked")

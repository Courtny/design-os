# Writing Style: Internal Audiences (Designers + PMs + Engineers)

Use this style for: design briefs, UX specs, critique notes, design review summaries, Slack messages to the team.

---

## Tone

- Conversational but precise. You're a colleague, not a consultant.
- Use "we" not "I." Design is a team sport.
- Direct and action-oriented. Say what you mean.
- OK to be informal. Short sentences. Even fragments. For emphasis.

## Structure

- Lead with context, then the "so what," then the detail.
- Bullet points over paragraphs where possible.
- Use headers when the doc is longer than one screen.
- Put edge cases and caveats in a separate section or footnote — don't bury them in the flow.

## Component and System Language

- Use exact component names from Storybook. Not "button" — `Button`, `ButtonGroup`.
- Reference props by name when relevant: "use the `helper-text` prop, not a separate `<p>` below the field."
- Call out when something is a new pattern vs. existing component.

## Specificity

- "Use the `DataTable` with `stickyHeader` enabled" beats "make the header sticky."
- Reference Storybook story paths or Figma frame links when you can.
- Include actual error messages, placeholder text, and empty states. Don't leave them for "later."

## What to Avoid

- Passive voice ("was decided," "it is recommended")
- Hedging ("might," "perhaps," "potentially")
- Filler ("as per our discussion," "in order to," "moving forward")
- Corporate jargon ("synergize," "leverage," "streamline")
- Em dashes. Use commas or periods instead.

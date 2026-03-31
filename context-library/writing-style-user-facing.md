# Writing Style: User-Facing Content

Use this style for: onboarding flows, tooltips, empty states, success messages, error messages, feature announcements, in-app guidance, release notes shown to users.

---

## Tone

- Clear, friendly, and confident. Not cute, not corporate.
- Talk to the user like a helpful colleague, not a robot or a salesperson.
- Encouraging without being patronizing. "You're all set" is fine. "Great job!" for clicking a button is not.

## Reading Level

- Aim for 8th grade reading level. Short sentences. Common words.
- If a simpler word works, use it. "Use" not "utilize." "Start" not "initiate." "Show" not "display."
- One idea per sentence. Break complex instructions into steps.

## Structure

- Lead with what the user gains, not what the system does.
  - Good: "See all your notifications in one place."
  - Not great: "The notification center aggregates alerts from multiple sources."
- Put the action first in instructions: "Click Save to keep your changes" not "To keep your changes, click Save."
- Use numbered steps for multi-step instructions. Use bullets for lists of options.

## Microcopy Rules

### Buttons and CTAs
- Verb-first: "Save changes," "Add member," "Start trial"
- Specific over generic: "Create project" beats "Submit." "Delete account" beats "Confirm."
- Sentence case always.

### Error Messages
- Say what happened, then how to fix it.
  - Good: "That email is already in use. Try signing in instead."
  - Bad: "Error: duplicate email detected."
- Never blame the user. The system had a problem, or the input needs adjusting.
- Include a recovery path whenever possible (a link, a suggestion, a "try again").

### Empty States
- Explain why it's empty (briefly).
- Give the user a clear next action.
  - Good: "No projects yet. Create your first project to get started."
  - Bad: "No data available."

### Success Messages
- Confirm what happened in the user's terms.
  - Good: "Your changes are saved."
  - Bad: "Operation completed successfully."
- Keep them brief. Success should feel lightweight, not ceremonial.

### Tooltips and Helper Text
- One sentence max. If it needs more, it belongs in documentation, not a tooltip.
- Explain why, not just what. "Appears on your public profile" is better than "Your display name."

### Loading and Wait States
- Under 300ms: no message needed.
- 300ms to 2s: subtle spinner only. No text.
- Over 2s: brief context. "Loading your dashboard..." not "Please wait while we fetch your data from our servers."

## What to Avoid

- Jargon the user wouldn't use: "payload," "endpoint," "instantiate," "deprecated"
- Exclamation marks in error states. Errors are not exciting.
- ALL CAPS for emphasis. Use bold or a different visual treatment.
- Placeholder text left in production: "[copy TBD]," "Lorem ipsum"
- Marketing language in product UI: "Unlock the power of..." "Supercharge your workflow..."
- Em dashes. Use commas, periods, or shorter sentences.

## Localization Awareness

- Avoid idioms that don't translate: "hit the ground running," "out of the box"
- Leave room for text expansion (some languages need 30-40% more space than English)
- Don't embed text in images
- Use ISO date formats or spell out the month when dates appear in UI

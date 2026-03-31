# Contributing to Design OS

Thanks for considering a contribution. Design OS is a toolkit for designers, and contributions from people who actually use it make it better.

## How to Contribute

### Reporting Issues

Open an issue if you find:
- A template that's missing a section you consistently need
- A foundation file with inaccurate information
- A skill that produces poor output (describe what you expected vs. what you got)
- Gaps in the toolkit (something that should exist but doesn't)

### Suggesting Additions

Open an issue or PR for:
- New foundation files (HCI concepts, interaction theory, visual craft references)
- New component UX files for common patterns
- New methodology docs (team process guides, workshop playbooks)
- Improvements to existing templates or skills

### Submitting Changes

1. Fork the repo
2. Create a branch: `git checkout -b add-[thing]`
3. Make your changes
4. Submit a PR with a clear description of what you added and why

## What Goes Where

| Content type | Location | Format |
|-------------|----------|--------|
| HCI concepts, interaction theory, visual craft | `context-library/foundations/` | Markdown, see existing files for structure |
| Component UX guidance | `context-library/design-system/component-ux/` | Follow `templates/component-ux-template.md` |
| Design process and methodology | `context-library/methodology/` | Markdown, practical over theoretical |
| Templates | `templates/` | Empty templates only, never filled out |
| Example specs | `context-library/example-specs/` | Realistic filled examples |
| Skills (slash commands) | `.claude/skills/[name]/SKILL.md` | Follow existing skill structure |
| Sub-agents | `sub-agents/` | Follow existing sub-agent structure |

## Writing Standards

Design OS has a specific voice. Before writing, read:
- `CLAUDE.md` sections 3 (Output Philosophy) and 4 (Writing Style Rules)
- `context-library/writing-style-internal.md` for tone reference

Key rules:
- **Short and specific.** Every section should help someone decide or build.
- **No em dashes.** Use commas, periods, or parentheses.
- **Sound human.** Vary sentence length. Use contractions. Skip filler phrases.
- **Avoid:** "delve," "leverage," "utilize," "unlock," "harness," "streamline," "robust," "cutting-edge"

## Foundation Files

If you're adding a foundation file (HCI concept, cognitive effect, design principle):

1. Check `context-library/foundations/README.md` to make sure it doesn't already exist
2. Follow the structure of existing files (see `fitts-law.md` or `cognitive-load.md` for good models)
3. Include: definition, why designers care, practical application, common misapplications, references
4. Add your file to the appropriate category in `foundations/README.md`

## Component UX Files

If you're adding a component UX file:

1. Copy `templates/component-ux-template.md` as your starting point
2. Name the file to match the Storybook component name exactly (lowercase, kebab-case)
3. Fill out all sections: when to use, do/avoid, states, accessibility, pairings, common mistakes
4. Add it to `context-library/design-system/component-ux/`

## Code of Conduct

Be respectful, constructive, and specific. Design is subjective, but UX guidance should be grounded in research, heuristics, or team experience, not just preference.

## Questions?

Open an issue. We're happy to help you figure out where a contribution fits.

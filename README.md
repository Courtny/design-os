# Design Operating System

**v1.0.0** | [Changelog](CHANGELOG.md) | [Roadmap](ROADMAP.md) | [Contributing](CONTRIBUTING.md) | [License](LICENSE)

Your AI-powered copilot for product design. Built for Claude Code and Cursor.

## Philosophy

Most designers use AI for one-off questions with zero context about their actual design system, past decisions, or research. This system works differently.

- **Context over prompting.** Design OS organizes your design system, UX principles, component guidance, research, and decisions so every output reflects how your team actually works.
- **Workflows, not chat.** Slash commands cover the full design loop: briefs, critiques, specs, research synthesis, accessibility reviews, and more.
- **Ship the draft, iterate.** A tight brief or one-page spec beats a 20-slide deck that never leaves Figma.

## What You Get

- **Design system context** - Storybook reference, Figma library links, principles, component-level UX guidance
- **Slash commands** - One-line prompts for repeatable design tasks
- **Sub-agents** - Specialized reviewers (PM alignment, engineering, content design, accessibility, brand)
- **Context library** - Templates for product context, writing styles, stakeholder profiles, research, decisions

## Quick Start

### 1. Install Claude Code

```bash
curl -fsSL https://claude.ai/install.sh | bash
claude --version
```

### 2. Set Up This Workspace

```bash
cd design-os
claude
```

> For a complete setup walkthrough (subscriptions, API keys, MCP configuration), see [`setup/first-session-checklist.md`](setup/first-session-checklist.md).

**Using Cursor instead of Claude Code?** See [`setup/cursor-setup.md`](setup/cursor-setup.md) for the full Cursor setup guide. The short version: open the `design-os` folder as your workspace, and reference skills with `@` instead of slash commands.

### 3. Connect Figma (Recommended)

```
/connect-mcps connect to figma
```

Figma has an official remote MCP server. No API keys needed: just run the command and authenticate.

### 4. Fill Out Your Context

- Product context: `context-library/product-context-template.md`
- Design system: `context-library/design-system/storybook.md` and `figma.md`
- Component UX guidance: `context-library/design-system/component-ux/`
- Writing styles: `context-library/writing-style-*.md`
- Example specs: `context-library/example-specs/` — reference examples that calibrate `/design-spec-draft` to your team's format and voice. Add 1–3 specs that represent your quality bar.

### 5. Try Your First Command

```
/ux-brief            # Start a new feature brief
/critique-prep       # Prep for a design critique
/design-spec-draft   # Draft a UX spec from a brief or PRD
/visual-critique     # Critique a design from an attached image
/figma-critique      # Critique a Figma file and optionally post comments
```

## Directory Structure

```
design-os/
├── README.md                         # You are here
├── CLAUDE.md                         # Master instructions for the AI copilot
├── LICENSE                           # MIT License
├── CONTRIBUTING.md                   # How to contribute
├── CHANGELOG.md                      # Version history
├── ROADMAP.md                        # Planned additions
│
├── .claude/                          # Claude Code configuration
│   └── skills/                       # Slash commands (13 skills)
│       ├── connect-mcps/             # Connect Figma, Storybook, and other tools
│       ├── ux-brief/                 # Create design briefs
│       ├── critique-prep/            # Prepare for design critiques
│       ├── design-spec-draft/        # Draft UX specs
│       ├── prototype/                # Generate working prototypes
│       ├── research-synthesis/       # Synthesize design research
│       ├── accessibility-review/     # WCAG and heuristic reviews
│       ├── meeting-notes/            # Critique and sync notes
│       ├── visual-critique/          # Critique a design from an image
│       ├── figma-critique/           # Critique a Figma file with optional commenting
│       ├── color-review/             # Semantic color and token review
│       ├── content-review/           # Microcopy and content hierarchy review
│       └── handoff-check/            # Pre-handoff spec completeness check
│
├── context-library/                  # Your design knowledge base
│   ├── product-context-template.md   # Product, users, and design constraints
│   ├── writing-style-*.md            # Writing styles (internal, executive, engineering, user-facing)
│   ├── stakeholder-template.md       # Stakeholder profiles
│   ├── design-system/                # Design system reference
│   │   ├── storybook.md              # Storybook URL, conventions, component index
│   │   ├── figma.md                  # Figma library links and usage norms
│   │   ├── principles.md             # Global UX and design principles
│   │   └── component-ux/             # Per-component UX guidance
│   ├── foundations/                   # HCI concepts, visual craft refs, prioritization frameworks
│   │   └── README.md                 # Topic index (37 files) — start here
│   ├── methodology/                  # Design process docs
│   │   ├── critique-norms.md         # How to run design critiques
│   │   └── handoff-checklist.md      # What "ready for engineering" means
│   ├── design-specs/                 # Completed or reference UX specs
│   ├── example-specs/                # Reference examples for spec drafting
│   ├── research/                     # Usability research, eval sessions, competitive UX
│   ├── decisions/                    # Design decision logs and ADRs
│   ├── meetings/                     # Critique notes, syncs, retros
│   └── launches/                     # Optional: design release notes and launch post-mortems
│
├── sub-agents/                       # Specialized review perspectives
│   ├── pm-alignment.md               # Product and strategy alignment
│   ├── engineering-feasibility.md    # Implementation concerns
│   ├── content-design.md             # Content and microcopy review
│   ├── accessibility-reviewer.md     # A11y and inclusive design
│   └── brand-reviewer.md             # Brand and visual consistency
│
├── templates/                        # Empty templates only
│   ├── ux-brief-template.md
│   ├── critique-agenda-template.md
│   ├── design-spec-template.md
│   ├── component-ux-template.md
│   ├── accessibility-checklist-template.md
│   ├── meeting-notes-template.md
│   ├── research-synthesis-template.md
│   └── decision-log-template.md
│
├── setup/                            # Installation and onboarding
│   ├── first-session-checklist.md    # Claude Code setup
│   └── cursor-setup.md              # Cursor IDE setup
│
└── outputs/                          # All active work (Claude writes here)
    ├── briefs/
    ├── design-specs/
    ├── prototypes/
    ├── critique-notes/
    ├── research-synthesis/
    ├── meeting-notes/
    ├── decisions/
    └── mcp-integration-logs/
```

## Available Slash Commands

Type `/` in Claude Code to see all commands.

### Core Design Workflows
- `/connect-mcps` - Connect Figma MCP and Storybook for real-time context
- `/ux-brief` - Create a design brief from a problem statement or PRD
- `/critique-prep` - Build a critique agenda with feedback prompts
- `/design-spec-draft` - Draft a UX spec with flows, states, and edge cases
- `/research-synthesis` - Turn usability sessions or research into insights
- `/accessibility-review` - WCAG and heuristic review tied to your principles
- `/meeting-notes` - Structure critique and design sync notes into action items

### Design Critique
- `/visual-critique` - Critique a design from an attached image (screenshot, export, or sketch photo). No MCP needed.
- `/figma-critique` - Critique a Figma file or frame. Reads live data via Figma MCP and optionally posts findings as Figma comments. Requires Figma MCP connected.

### Quality and Review
- `/color-review` - Review color usage for semantic consistency, token adherence, and accessibility. Grounded in your `principles.md` tokens and `foundations/semantic-color.md`.
- `/content-review` - Review microcopy, labels, error messages, and content hierarchy against your writing style files and content rules.
- `/handoff-check` - Pre-handoff completeness check. Verifies a UX spec has everything engineering needs to build without asking questions.
- `/tufte-viz` - Ideate or critique charts and dashboards using Tufte principles. Grounded in `foundations/tufte-principles.md`.

See [`ROADMAP.md`](ROADMAP.md) for planned additions.

## Key Design System Links

| Resource | Where to Look |
|----------|---------------|
| Component library (live) | `context-library/design-system/storybook.md` |
| Design files (exploration) | `context-library/design-system/figma.md` |
| UX principles | `context-library/design-system/principles.md` |
| Component UX guidance | `context-library/design-system/component-ux/` |
| Example specs (format + voice) | `context-library/example-specs/` |
| HCI laws and frameworks index | `context-library/foundations/README.md` |

## Conflict Resolution

**Storybook = production truth.** If Storybook and Figma differ, Storybook wins for implementation.
Figma is exploratory unless a file or frame is explicitly labeled "approved" or "shipped."

## Pro Tips

1. **Connect Figma first** - Run `/connect-mcps connect to figma` before anything else.
2. **Fill component UX files** - The richer your `component-ux/` guidance, the better specs you'll get.
3. **Add example specs early** - Drop 1–3 real specs into `example-specs/` so the copilot matches your team's format and detail level from the start.
4. **Paste research transcripts** - Run `/research-synthesis` on raw session notes.
5. **Dictate briefs** - Talk through a brief out loud with dictation. Much faster than typing.
6. **Name files consistently** - Match component names in `component-ux/` to Storybook component names exactly.
7. **Browse foundations by topic** - `context-library/foundations/README.md` is the index. Find Fitts's Law, cognitive load, Gestalt, and 30+ more by category.

---

**Ready to start? Run `/connect-mcps connect to figma`, fill out `context-library/product-context-template.md`, add a spec or two to `context-library/example-specs/`, and try `/ux-brief`.**

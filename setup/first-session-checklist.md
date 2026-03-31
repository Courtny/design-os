# First Session Checklist

Get Design OS running in about 30 minutes. Don't try to do everything at once — prioritize by what you'll use first.

---

## Step 1: Install Claude Code (5 min)

```bash
curl -fsSL https://claude.ai/install.sh | bash
claude --version
```

You'll need a Claude Pro ($20/mo) or Claude Max ($100–200/mo) subscription, or an Anthropic API key from [console.anthropic.com](https://console.anthropic.com).

To set an API key:
```bash
export ANTHROPIC_API_KEY='your-key-here'
# Make it permanent:
echo 'export ANTHROPIC_API_KEY="your-key-here"' >> ~/.zshrc
```

---

## Step 2: Open Design OS in Claude Code (1 min)

```bash
cd ~/Documents/design-os   # or wherever you put this folder
claude
```

Claude Code reads `CLAUDE.md` automatically. You're ready to work.

---

## Step 3: Connect Figma (5 min) — Recommended

Figma has an official remote MCP server. No API key required.

In your terminal:
```bash
claude mcp add --transport http figma https://mcp.figma.com/mcp
```

In Claude Code, type `/mcp` and authenticate with your Figma account.

That's it. Now you can ask things like:
- "What's in my [design file]?"
- "Show me the latest comments on the checkout redesign"
- "What components are in our Figma library?"

If you'd rather skip this for now, everything in Design OS works without Figma MCP using the file links in `context-library/design-system/figma.md`.

---

## Step 4: Fill Out Product Context (10 min)

Open `context-library/product-context-template.md` and fill it out. At minimum:
- Product name and what it does
- Primary user description
- Platform(s)
- Design constraints (stack, responsive requirements, brand constraints)

This is what the copilot reads when you ask questions or generate work. The more specific, the better.

---

## Step 5: Add Design System Info (10 min)

**Storybook:**
Open `context-library/design-system/storybook.md`:
- Add your Storybook URL
- Note whether it's public, VPN-only, or auth-gated
- Add your component naming conventions (if different from the defaults)

**Figma:**
Open `context-library/design-system/figma.md`:
- Add your design library file URL
- Add your key feature file links

**Principles:**
Open `context-library/design-system/principles.md`:
- Add your team's actual UX principles (not generic ones — yours)
- Update the accessibility section if your standard differs from WCAG 2.1 AA

---

## Step 6: Add Component UX Guidance (ongoing)

Start with your 5 most-used components. For each one:
1. Copy `templates/component-ux-template.md`
2. Save it to `context-library/design-system/component-ux/[component-name].md`
3. Fill in: when to use, do/avoid, states, accessibility, pairings

Two example files are already there as models: `button.md` and `form-field.md`.

---

## Step 7: Try Your First Command

```
/ux-brief
```

I'll ask you a few questions and generate a design brief. Takes 10–15 minutes for the first one.

---

## Optional: Connect More Tools

Run these anytime you're ready:

```
/connect-mcps connect to dovetail   # Research repository
/connect-mcps connect to linear     # Design tasks and tickets
/connect-mcps connect to slack      # Team communications
```

---

## Ongoing: Build Your Context Library

Design OS gets smarter as you add context. Priority order for what to add next:

1. **Component UX guidance** — `context-library/design-system/component-ux/`
2. **Research** — `context-library/research/`
3. **Decisions** — `context-library/decisions/`
4. **Past specs** — `context-library/design-specs/`
5. **Example specs** — `context-library/example-specs/`
6. **Stakeholder profiles** — `context-library/stakeholder-template.md`
7. **Foundations** — `context-library/foundations/` (interaction concepts, craft references, prioritization frameworks)
8. **Methodology** — `context-library/methodology/` (team process: critiques, discovery, sprints, handoffs)

---

## Quick Command Reference

| Command | What it does |
|---------|-------------|
| `/ux-brief` | Create a design brief |
| `/critique-prep` | Prepare a critique agenda |
| `/design-spec-draft` | Draft a UX spec |
| `/research-synthesis` | Synthesize session notes |
| `/accessibility-review` | WCAG and heuristic review |
| `/meeting-notes` | Process critique or sync notes |
| `/connect-mcps connect to figma` | Connect Figma MCP |

---

## Exposing Storybook for Design OS

If your Storybook is private (VPN-only or auth-gated), the copilot can't fetch it directly. You have two options:

**Option A: Keep it private, use docs**
Add component names, variants, and links to `context-library/design-system/storybook.md`. The copilot reads that file and references it without needing to fetch the live URL. Works great in practice.

**Option B: Expose a design-copilot deploy**
Create a dedicated Storybook deploy with appropriate auth (SSO, IP allowlist) that the copilot can access via fetch tools. Discuss with your security team before doing this. Add the URL to `storybook.md` when ready.

Start with Option A. It covers 90% of what you'll need.

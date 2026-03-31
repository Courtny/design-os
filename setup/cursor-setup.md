# Cursor Setup Guide

Design OS works in Cursor as well as Claude Code. This guide covers how to set it up in Cursor specifically.

---

## Step 1: Open the Workspace

Open the `design-os` folder as your workspace in Cursor:

```
File > Open Folder > design-os/
```

Cursor reads `CLAUDE.md` automatically as project-level context. Every conversation in this workspace will have access to your design system references, principles, and writing rules.

---

## Step 2: How Skills Work in Cursor

In Claude Code, skills are slash commands (type `/ux-brief` and go). In Cursor, skills are files that you reference in your chat or Composer.

**To use a skill in Cursor:**

1. Open Cursor's chat or Composer
2. Reference the skill by typing `@` and selecting the file, or paste the description directly

For example, to run the UX brief skill:
- Type: `@.claude/skills/ux-brief/SKILL.md` followed by your request
- Or simply describe what you want: "Create a UX brief for [feature]" and the agent will find and follow the skill automatically if you have the skills folder visible

**Available skills and their file paths:**

| Skill | Path |
|-------|------|
| UX Brief | `.claude/skills/ux-brief/SKILL.md` |
| Design Spec Draft | `.claude/skills/design-spec-draft/SKILL.md` |
| Critique Prep | `.claude/skills/critique-prep/SKILL.md` |
| Research Synthesis | `.claude/skills/research-synthesis/SKILL.md` |
| Accessibility Review | `.claude/skills/accessibility-review/SKILL.md` |
| Meeting Notes | `.claude/skills/meeting-notes/SKILL.md` |
| Visual Critique | `.claude/skills/visual-critique/SKILL.md` |
| Figma Critique | `.claude/skills/figma-critique/SKILL.md` |
| Color Review | `.claude/skills/color-review/SKILL.md` |
| Content Review | `.claude/skills/content-review/SKILL.md` |
| Handoff Check | `.claude/skills/handoff-check/SKILL.md` |
| Prototype | `.claude/skills/prototype/SKILL.md` |
| Connect MCPs | `.claude/skills/connect-mcps/SKILL.md` |

---

## Step 3: Connect Figma MCP in Cursor

Cursor supports MCP servers. To connect Figma:

1. Open Cursor Settings (Cmd+, on Mac)
2. Navigate to the MCP section
3. Add a new MCP server with these settings:
   - **Name:** Figma
   - **Transport:** HTTP
   - **URL:** `https://mcp.figma.com/mcp`
4. Authenticate with your Figma account when prompted

Once connected, you can ask Cursor to read Figma files, pull comments, and list components directly in chat.

If you prefer not to connect Figma MCP, everything still works using the file links in `context-library/design-system/figma.md`.

---

## Step 4: Fill Out Your Context

Same as Claude Code. Complete these files:

1. **Product context:** `context-library/product-context-template.md`
2. **Design system:** `context-library/design-system/storybook.md` and `figma.md`
3. **Principles:** `context-library/design-system/principles.md`
4. **Component UX:** `context-library/design-system/component-ux/` (start with your 5 most-used components)
5. **Example specs:** `context-library/example-specs/` (add 1-3 real specs)

See `context-library/example-specs/example-product-context.md` for a filled example.

---

## Step 5: Try It

Open Cursor chat and try:

- "Create a UX brief for a new search feature"
- "Review this design for accessibility" (attach an image)
- "Draft a spec for the onboarding flow based on this brief" (reference a brief file)

---

## Cursor vs. Claude Code: Key Differences

| Feature | Claude Code | Cursor |
|---------|------------|--------|
| Skills (slash commands) | Type `/skill-name` | Reference the skill file with `@` or describe the task |
| CLAUDE.md context | Automatic | Automatic |
| MCP connections | Terminal command (`claude mcp add`) | Cursor Settings > MCP |
| File creation | Writes to `outputs/` automatically | Same behavior in Agent/Composer mode |
| Image input | Attach images to chat | Attach images to chat |
| Sub-agents | Spawn automatically when asked | Work the same way |

---

## Tips for Cursor Users

1. **Pin the context library.** Keep `context-library/` visible in your file explorer so you can quickly `@`-reference files.
2. **Use Composer for multi-file tasks.** When generating specs or briefs that reference multiple context files, Composer mode handles the context better.
3. **Attach images for visual critique.** Drag a screenshot into chat and ask for a visual critique. The copilot reads your `principles.md` and `component-ux/` files automatically.
4. **Keep outputs organized.** The copilot writes to `outputs/` by default. Promote finalized work to `context-library/` when it's done.

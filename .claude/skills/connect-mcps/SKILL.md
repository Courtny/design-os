---
name: connect-mcps
description: Connect MCPs for real-time tool integration — Figma (primary), Storybook, research tools, and project management
version: 1.0
user-invocable: true
modifies-workspace: true
---

# `/connect-mcps` - MCP Integration for Design OS

Connect Model Context Protocol servers to your Design OS workspace for live access to Figma, research tools, and project management.

## Quick Start

```
/connect-mcps connect to figma      # Start here — official remote MCP, no API key needed
/connect-mcps connect to dovetail   # User research repository
/connect-mcps connect to linear     # Design tickets and tasks
/connect-mcps connect to slack      # Team communication
```

**Figma is the priority.** It has an official remote MCP server — the easiest possible setup.

---

## Figma (Start Here)

Figma has an official remote MCP server at `https://mcp.figma.com/mcp`.

When you run `/connect-mcps connect to figma`:

1. I'll confirm the remote server URL
2. Give you this command to run in your terminal:
   ```bash
   claude mcp add --transport http figma https://mcp.figma.com/mcp
   ```
3. In Claude Code, type `/mcp` to see your connected MCPs
4. Select Figma and authenticate with your Figma account
5. Done — no API keys, no manual config

**Once connected, you can ask:**
- "What's in the [file name] Figma file?"
- "Show me the latest comments on the dashboard design"
- "What components are in our design library?"
- "What's the current state of the checkout flow?"

**Fallback:** If Figma MCP is not connected, use the file links in `context-library/design-system/figma.md` and describe what you need.

---

## Other Supported Tools

### Dovetail (User Research)

Research repository for usability session notes, themes, and insights.

**What it enables:**
- "Find all research on the navigation pattern"
- "Show me quotes about filter UX from user interviews"
- "What themes came up in Q1 usability studies?"

**Setup:** Search for official Dovetail MCP docs when connecting. Usually requires an API token from Dovetail settings.

**Fallback:** Upload research synthesis to `context-library/research/` and I'll read it from there.

### Linear (Design Tickets)

Track design tasks, file bugs, and check engineering progress.

**What it enables:**
- "Show my open design tickets"
- "Create a ticket for the FilterBar accessibility fix"
- "What's the status of the checkout redesign ticket?"

**Setup:** Linear usually has a remote MCP or NPM package. Requires a Personal API Key from Linear Settings → API.

**Fallback:** Track action items in `context-library/meetings/`.

### Slack

Search design discussions, post summaries, or draft announcements.

**What it enables:**
- "Find the conversation about the nav pattern from last Tuesday"
- "Post the critique summary to #design-team"

**Setup:** Requires OAuth token from Slack app settings.

**Fallback:** Draft messages in `outputs/` and copy manually.

---

## How Connection Works

For each tool:

1. **Check for a remote MCP server first** — search for `[tool] official MCP server 2026`
2. **If remote exists:** Use `claude mcp add --transport http [tool] [url]`, then auth via `/mcp`
3. **If no remote server:** Research NPM/local setup and walk you through credentials
4. **Test the connection** — verify with a simple query
5. **Map to skills** — update relevant Design OS skills with MCP integration instructions
6. **Update CLAUDE.md registry** — so routing is automatic for future queries
7. **Save integration log** to `outputs/mcp-integration-logs/[date]-[tool].md`

---

## After Connecting

Once MCPs are connected, just ask naturally:

- "What's in the checkout Figma file?" → routes to Figma MCP
- "Find research on the filter pattern" → routes to Dovetail MCP
- "Show my open design tasks" → routes to Linear MCP
- "Find the Slack thread about the nav redesign" → routes to Slack MCP

I handle the routing automatically based on your question.

---

## MCPs Are Optional

Every skill in Design OS works without MCPs using file-based context. MCPs add live data and speed; they don't unlock gated features.

Add them when you're ready. Start with Figma.

---

## Troubleshooting

**Figma MCP not showing up after running the add command:**
- Restart Claude Code
- Run `/mcp` to refresh the list
- Verify the URL: `https://mcp.figma.com/mcp`

**Connection test fails:**
- Double-check credentials (no extra spaces)
- Confirm API key has read permissions
- Try the API in the tool's web interface first

**Queries not routing to the right MCP:**
- Check CLAUDE.md → MCP Integrations → confirm the tool is in the registry
- Try being explicit: "Use Figma to show me the checkout file"

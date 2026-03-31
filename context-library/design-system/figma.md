# Figma Reference

Figma is where we explore, iterate, and annotate. It is **not** the production source of truth for components — Storybook is. Use Figma files for flows, concepts, and annotations; verify components against Storybook before handing off.

**Conflict rule:** When a Figma frame and a Storybook component differ in behavior or appearance, Storybook wins for implementation. Figma is exploratory unless a frame is explicitly labeled "approved" or "shipped."

---

## Figma MCP

This workspace supports the **Figma MCP** for live file access during design sessions.

**To connect:**
```
/connect-mcps connect to figma
```

**What the MCP enables:**
- "What's in the checkout flow file?" → reads the Figma file directly
- "Show me the latest comments on the dashboard redesign" → pulls comment threads
- "What components are used in this frame?" → lists components with Figma names
- "Export the mobile mockups" → makes frames available for review

**Fallback:** If the MCP is not connected, use the direct file links below.

---

## Key Files

Fill these in during setup. Keep them updated as you create new files.

### Design System Library

**Library file URL:**
_[Fill in: your Figma library file link]_

**What's in it:**
<!-- e.g., All published components matching Storybook, color/typography styles, spacing grid, icon set -->

**Sync cadence:**
<!-- e.g., Updated monthly. Storybook is source of truth; Figma library reflects it after syncs. -->

**File maintainer:**
_[Fill in: name and Slack handle]_

---

### Active Feature Files

Keep this table updated with your current design work.

| Feature | File | Status | Last updated |
|---------|------|--------|--------------|
| _[Example: Onboarding redesign]_ | _[Figma link]_ | In progress | _[date]_ |
| | | | |

---

### Archive / Reference Files

Files for shipped features or past explorations. Good reference for patterns and decisions.

| Name | File | Notes |
|------|------|-------|
| | | |

---

## Figma Conventions

### File Naming

`[Feature or area] — [Status]`

Examples:
- `Checkout Redesign — In Review`
- `Dashboard v2 — Shipped`
- `Component: FilterBar — Exploration`

### Frame and Layer Naming

- Screens: `[Platform] / [Flow] / [Step]` — e.g., `Web / Onboarding / Step 2 - Email`
- Components: match the Storybook component name exactly
- Annotation layers: prefix with `[Spec]` — e.g., `[Spec] Focus order`

### Status Labels (use these in frame titles)

| Label | Meaning |
|-------|---------|
| `Exploration` | Early ideas, not for review |
| `In Review` | Ready for critique or PM review |
| `Approved` | Aligned with PM/stakeholders, ready for handoff |
| `Shipped` | In production |
| `Archived` | No longer active |

---

## Component Usage Notes

Figma components are linked to the design library. When a Storybook component and a Figma component have different names, use this mapping:

| Figma Name | Storybook Name | Notes |
|------------|----------------|-------|
| _[example: Input / Text]_ | `TextInput` | Figma uses category prefix |
| | | |

---

## Handoff Checklist (Before Marking "Approved")

- [ ] All components match Storybook equivalents (or new pattern is explicitly called out)
- [ ] All states covered (default, hover, focus, error, loading, empty, disabled)
- [ ] All microcopy written out (no "[copy TBD]")
- [ ] Responsive variants present for each breakpoint
- [ ] Accessibility annotations added (focus order, ARIA notes)
- [ ] Linked to the UX spec in `outputs/design-specs/` or `context-library/design-specs/`

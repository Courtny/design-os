---
name: figma-critique
description: Critique a Figma file or frame using the Figma MCP. Reads live file data, runs a structured design critique, and optionally posts findings as comments back to Figma.
version: 1.0
user-invocable: true
requires-mcp: figma
---

# `/figma-critique` - Figma Design Critique

Critique a Figma file or specific frame using live file data from the Figma MCP. Produces a structured critique and optionally posts findings as comments directly in Figma.

## Quick Start

```
/figma-critique [figma URL]                        → Critique the full file or frame at that link
/figma-critique [figma URL] comment                → Critique + offer to post findings as Figma comments
/figma-critique [figma URL] [context]              → Best path: link + what you're reviewing and what decisions are open
```

**Output:** Critique saved to `outputs/critique-notes/[feature]-figma-critique-[date].md`
**Requires:** Figma MCP connected (see fallback below if not)
**Time:** 15–20 minutes

---

## MCP Dependency Check

**First action:** Check whether the Figma MCP is connected.

If Figma MCP is connected:
- Use `get_file` to read the file structure, frame names, and component instances
- Use `get_comments` to read existing comment threads for context
- Proceed with the critique framework below

If Figma MCP is NOT connected:
- Tell the designer: "Figma MCP isn't connected. Run `/connect-mcps connect to figma` to get set up — it's the official Figma remote MCP and only takes a minute. Once connected, come back and run `/figma-critique` again."
- Offer fallback: "If you want feedback now, export the frame as an image and run `/visual-critique` instead."
- Stop here. Don't proceed without the MCP.

---

## Context Routing (Internal)

Before reviewing, check:

| Source | Files/Folders | What to extract |
|--------|---------------|-----------------|
| Figma MCP | Linked file or frame | File structure, component instances, layer naming, existing comments |
| Principles | `context-library/design-system/principles.md` | Core UX principles and anti-patterns to check against |
| Component UX | `context-library/design-system/component-ux/` | Rules and states for components identified in the Figma file |
| Storybook | `context-library/design-system/storybook.md` | What's in the component library — to identify custom-drawn vs. library components |
| Figma library | `context-library/design-system/figma.md` | Team's Figma library file links and naming conventions |
| Research | `context-library/research/` | Known user expectations or pain points for this area |
| Brief or spec | `outputs/briefs/` or described in chat | Open decisions, scope, success criteria |

---

## Guided Questions

Ask these if the designer hasn't provided context:

1. "What is this file or frame? (Feature name, flow, component)"
2. "What stage is this? (Exploration, lo-fi, hi-fi, ready for handoff)"
3. "What specific decisions do you need feedback on?"
4. "What's already decided and not up for debate?"
5. "Do you want me to post findings as Figma comments after the critique?"

---

## What to Read from Figma

Work through the file or frame systematically using MCP tools:

### File Structure
- Read the top-level page and frame structure
- Note how the file is organized: by flow, by state, by component?
- Flag if the organization would confuse an engineer reading it for handoff

### Component Instances
- Identify component instances in the frames
- Cross-reference against `storybook.md` and `figma.md` — are these from the official library?
- Flag any components that appear to be manually recreated rather than using library instances
- Flag detached instances (components that were unlinked from the library)

### Layer and Frame Naming
- Are layers named meaningfully or left as "Frame 247," "Rectangle 12"?
- Are frames named in a way that maps to user flows or states?
- Flag naming that would make handoff harder for engineers

### Existing Comments
- Read any open comment threads — they signal known issues or open decisions
- Reference them in the critique where relevant: "There's already an open comment about X — this finding is related"
- Don't duplicate what's already raised in comments

---

## Critique Framework

Run the same visual and UX critique as `/visual-critique`, plus the Figma-specific checks above.

### 1. Visual Hierarchy
- Is there a clear primary action or focal point per frame?
- Does visual weight match importance?
- Does anything compete with the primary CTA?

### 2. Spacing and Grid
- Does spacing appear to follow a consistent scale?
- Are related elements grouped, unrelated elements separated?
- Flag anything misaligned or arbitrarily spaced.

### 3. Component Usage
- For each library component identified: does its usage match the guidance in `component-ux/`?
- Are there custom-drawn patterns where library components should be used?
- Note any components being used outside their documented intent.

### 4. Typography
- Is type scale consistent across frames?
- Does hierarchy read clearly?
- Flag any text below 12px or with low contrast.

### 5. Color and Contrast
- Do colors match the team's defined palette?
- Flag any text-on-background combinations that look low contrast.
- Flag color used as the sole state indicator.

### 6. Microcopy
- Are labels, CTAs, and headings specific and verb-led?
- Are any placeholder labels, TBD copy, or lorem ipsum still in the file?
- Does the tone match the team's voice?

### 7. State Coverage
- Which states are represented in the file? (Default, error, empty, loading, disabled)
- Which states are missing from the frames shown?
- Are error states specific and actionable?

### 8. Accessibility (Visible Issues)
- Touch target sizes, focus indicators in hi-fi, color-only state indicators
- Unlabeled icon buttons or missing text alternatives
- Missing contrast between interactive and non-interactive elements

### 9. Handoff Readiness (Figma-specific)
- Are all frames labeled clearly?
- Are component instances from the library (not manually recreated)?
- Are any measurements or annotations present where they'd help engineers?
- Would an engineer be able to navigate this file without a walkthrough?

---

## Comment Posting (Optional)

After the critique is drafted, ask the designer: "Want me to post these findings as comments in Figma?"

### If yes and the MCP supports write tools:

- Post one comment per finding, placed on the relevant frame or element
- Comment format: `[Severity] [Finding title]: [1–2 sentence observation and recommendation]`
- Group related findings on the same frame rather than cluttering with many small comments
- Post a summary comment at the file level: "Visual critique complete. [N] findings posted. See critique doc: [path to outputs file]"

### If yes and the MCP does not support comment posting:

- Tell the designer: "The Figma MCP I'm connected to doesn't support posting comments yet. Here's a comment-ready version of the findings you can paste directly into Figma:"
- Output each finding in this format, ready to copy:

```
[Frame name] — [Severity]
[Finding title]: [Observation]. [Recommendation].
```

---

## Output Structure

```markdown
# Figma Critique: [Feature or File Name]

**Date:** [date]
**Stage:** [exploration / lo-fi / hi-fi / handoff-ready]
**Platform:** [web / iOS / Android / all]
**Figma source:** [URL]
**Comments posted:** [yes / no / comment-ready block below]

---

## Summary

[2–3 sentences on overall quality and the most important opportunities.]

---

## Findings

| # | Location (frame/layer) | Observation | Recommendation | Ties to |
|---|------------------------|-------------|----------------|---------|
| 1 | [frame or layer name] | [what's happening] | [specific fix] | [principle or component-ux rule] |

---

## Figma-Specific Observations

[Layer naming, component library coverage, handoff readiness, any detached instances.]

---

## What's Working Well

[Specific things to preserve.]

---

## Missing States or Gaps

[States, edge cases, or flows not shown in the file.]

---

## Open Questions

[Things that can't be resolved from the file alone.]

---

## Comment-Ready Block (if not posted to Figma)

[One block per finding, formatted to paste directly into Figma comments.]

---

## Suggested Next Steps

[1–3 concrete actions. Link to relevant skill if applicable, e.g., "Run `/accessibility-review` before handoff."]
```

---

## Quality Check Before Saving

- [ ] Figma MCP connection confirmed before starting
- [ ] Existing comment threads read and referenced where relevant
- [ ] Component library coverage checked against `storybook.md` and `figma.md`
- [ ] Principles and `component-ux/` files checked before writing findings
- [ ] Findings tied to specific frame or layer names (not just "the design")
- [ ] Handoff readiness section complete for hi-fi or handoff-stage work
- [ ] Comment posting step offered to designer and handled (posted or comment-ready block included)
- [ ] Output saved to `outputs/critique-notes/`

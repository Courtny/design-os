---
name: accessibility-review
description: Heuristic and WCAG 2.1 AA accessibility review of UX specs, Figma flows, or described interactions. Tied to your design system's accessibility standards.
version: 1.0
user-invocable: true
---

# `/accessibility-review` - Accessibility Review

Systematic accessibility review of design work before engineering handoff.

## Quick Start

```
/accessibility-review                          → Review a spec I'll help you describe
/accessibility-review [paste spec or describe flow]  → I'll run the review
/accessibility-review [Figma link]             → I'll review the flow (requires Figma MCP)
```

**Output:** Review saved to `outputs/design-specs/[feature]-a11y-review-[date].md`
**Standard:** WCAG 2.1 AA (unless your `principles.md` specifies otherwise)
**Time:** 15–20 minutes per flow or spec

---

## Context Routing (Internal)

Before reviewing, check:

| Source | Files/Folders | What to extract |
|--------|---------------|-----------------|
| Accessibility standards | `context-library/design-system/principles.md` | Team's specific AA requirements and any exceptions |
| Component accessibility | `context-library/design-system/component-ux/` | Existing accessibility rules for components being used |
| Spec | `outputs/design-specs/` or described in chat | The flow, states, and components being reviewed |
| Figma MCP (if connected) | Linked file | Live view of the design being reviewed |

---

## Review Framework

### Guided Questions

1. "What are you reviewing? (spec, Figma flow, described interaction)"
2. "What platform? (web, iOS, Android)"
3. "What's the user flow from entry to completion?"
4. "What interactive elements are present?"

---

### Review Areas

Work through each area systematically. Flag issues with severity and the WCAG criterion.

#### 1. Keyboard Navigation

- Can all interactive elements be reached via Tab in a logical order?
- Does focus order match visual/reading order?
- Is there a keyboard trap anywhere (e.g., dialog or modal)?
- Can the user exit any focused component with Escape?
- Are all actions achievable without a mouse?
- Do custom components (if any) implement standard keyboard patterns?

**WCAG criteria:** 2.1.1 (Keyboard), 2.1.2 (No Keyboard Trap), 2.4.3 (Focus Order)

#### 2. Focus Visibility

- Is the focus indicator visible on all interactive elements?
- Does the focus indicator meet 3:1 contrast ratio against adjacent background?
- Does the spec explicitly NOT use `outline: none` without a replacement?

**WCAG criterion:** 2.4.7 (Focus Visible), 2.4.11 (Focus Appearance — AA 2.2)

#### 3. Screen Reader Compatibility

- Do all images have meaningful `alt` text? (Decorative: `alt=""`)
- Do all form inputs have associated visible `<label>` elements?
- Are error messages programmatically associated with their input (`aria-describedby`)?
- Do icons used as buttons have `aria-label`?
- Are status messages and dynamic content changes announced (`aria-live`)?
- Is there a logical heading hierarchy (one `<h1>`, logical h2/h3 nesting)?

**WCAG criteria:** 1.1.1 (Non-text Content), 1.3.1 (Info and Relationships), 4.1.3 (Status Messages)

#### 4. Color and Contrast

- Normal text: 4.5:1 minimum contrast against background
- Large text (18px+ or 14px+ bold): 3:1 minimum
- UI components and focus indicators: 3:1 minimum against adjacent color
- Is information conveyed by color alone? (Error state, status badge, etc.) If so, a secondary indicator is required.

**WCAG criteria:** 1.4.3 (Contrast Minimum), 1.4.11 (Non-text Contrast), 1.4.1 (Use of Color)

#### 5. Touch and Pointer

- Are touch targets at least 44×44 CSS px?
- Does any interaction require hovering? (hover-only affordances fail on mobile)
- Do multi-step gestures (swipe, pinch) have button alternatives?

**WCAG criteria:** 2.5.5 (Target Size), 2.5.3 (Pointer Gestures)

#### 6. Motion and Animation

- Do animations that convey information work without motion? (respect `prefers-reduced-motion`)
- Does anything flash more than 3 times per second?

**WCAG criteria:** 1.4.2 (Audio Control), 2.3.1 (Three Flashes)

#### 7. Content and Copy

- Do error messages say what went wrong AND how to fix it?
- Do empty states explain why and give a clear next action?
- Are loading states communicated to screen readers (not just visual)?
- Is link text meaningful out of context? ("Learn more about X" not just "click here")

**WCAG criteria:** 2.4.6 (Headings and Labels), 3.3.1 (Error Identification), 3.3.3 (Error Suggestion)

#### 8. Forms

- All inputs have visible labels (not just placeholder)
- Required fields marked (`isRequired` prop or equivalent)
- Error validation messages are inline, specific, and programmatically associated
- Groups (checkbox sets, radio groups) use `<fieldset>` + `<legend>` (or `RadioGroup`/`CheckboxGroup`)

**WCAG criteria:** 1.3.5 (Identify Input Purpose), 3.3.2 (Labels or Instructions)

---

## Severity Classification

| Severity | Meaning | When to fix |
|----------|---------|-------------|
| **Critical** | Blocks access for users with disabilities. Cannot complete the task. | Before launch |
| **Serious** | Significant barrier. Frustrating or difficult but not completely blocking. | This release |
| **Minor** | Usability degradation for some users. Task completable with effort. | Next iteration |
| **Enhancement** | Goes beyond AA; WCAG AAA or best practice. | Backlog |

---

## Output Structure

```markdown
# Accessibility Review: [Feature Name]

Date: [date]
Reviewer:
Standard: WCAG 2.1 AA
Spec / Figma: [link]

---

## Summary

[1–2 sentences: overall accessibility quality and key concerns]

Critical issues: [#]
Serious issues: [#]
Minor issues: [#]
Enhancements: [#]

---

## Issues

### Issue 1: [Short description]

Severity: Critical / Serious / Minor
WCAG: [criterion number and name]
Location: [screen, component, or state]

What's wrong:
[Specific description of the problem]

How to fix:
[Specific, actionable fix. Reference Storybook component or prop if applicable.]

---

## What's Working Well

[Specific accessibility decisions in the design that are solid and should be preserved]

---

## Sign-off Checklist

- [ ] All critical issues resolved
- [ ] Serious issues have remediation plan with owner and date
- [ ] Minor issues logged for next iteration
```

---

## Quality Check Before Saving

- [ ] All 8 review areas covered
- [ ] Each issue has a severity, WCAG criterion, location, and specific fix
- [ ] "What's working" section included (not just problems)
- [ ] Sign-off checklist included
- [ ] Critical issues are clearly flagged — cannot be missed

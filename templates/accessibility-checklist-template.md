# Accessibility Review Checklist: [Feature Name]

**Reviewer:**
**Date:**
**Spec / Figma:** _[link]_
**Standard:** WCAG 2.1 AA

---

## Keyboard Navigation

- [ ] All interactive elements reachable via Tab in logical order
- [ ] Focus order matches visual and reading order
- [ ] Focus indicator clearly visible on all interactive elements (3:1 contrast ratio)
- [ ] All actions achievable without a mouse (Enter, Space, Arrow keys where appropriate)
- [ ] No keyboard traps — user can exit any component or dialog with Escape or Tab
- [ ] Modal / dialog traps focus inside until dismissed (intentional trap)
- [ ] Skip navigation link present for pages with long nav (or equivalent)

---

## Screen Readers

- [ ] All images have meaningful `alt` text (`alt=""` for decorative)
- [ ] All form inputs have associated visible `<label>` elements
- [ ] Error messages programmatically associated with their input (`aria-describedby`)
- [ ] Icons used as buttons have `aria-label`
- [ ] Status messages use `aria-live="polite"` (or `assertive` for urgent alerts)
- [ ] Page has one `<h1>`; heading hierarchy is logical (h1 → h2 → h3)
- [ ] Table headers use `<th>` with `scope` attribute
- [ ] Form groups use `<fieldset>` + `<legend>`
- [ ] Dynamic content changes are announced to screen readers

---

## Color and Contrast

- [ ] Normal text contrast: 4.5:1 minimum
- [ ] Large text contrast (18px+ or 14px+ bold): 3:1 minimum
- [ ] UI component and focus indicator contrast: 3:1 minimum
- [ ] Information is not conveyed by color alone (e.g., error state has both red color AND error message text)
- [ ] Links distinguishable from body text by more than color (underline or weight)

---

## Touch and Pointer

- [ ] Touch targets at least 44×44px (WCAG 2.5.5)
- [ ] No action requires a hover-only interaction
- [ ] Pointer gestures (swipe, pinch) have keyboard or button alternatives

---

## Motion and Animation

- [ ] Purely decorative animations respect `prefers-reduced-motion`
- [ ] No content flashes more than 3 times per second (seizure risk)
- [ ] Animations do not block access to content or actions

---

## Content

- [ ] Error messages say what went wrong AND how to fix it
- [ ] Empty states explain why the view is empty and what to do
- [ ] Loading states are communicated to screen readers (not just visual spinner)
- [ ] Time limits have a warning or can be extended (WCAG 2.2.1)

---

## Issues Found

| # | Issue | Severity | WCAG Criterion | Recommendation |
|---|-------|----------|---------------|----------------|
| 1 | | Critical / Serious / Minor | | |
| 2 | | | | |

**Severity guide:**
- **Critical:** Blocks access for users with disabilities. Must fix before launch.
- **Serious:** Significant barrier. Fix in this release or immediately after.
- **Minor:** Usability degradation. Fix in next iteration.

---

## Sign-off

- [ ] All critical issues resolved
- [ ] Serious issues have a remediation plan with a date
- [ ] Minor issues logged for next iteration

**Reviewed by:**
**Date cleared:**

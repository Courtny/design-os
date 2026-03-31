# UX Spec: Account settings — profile form validation (example)

**Author:** Design OS (example)  
**Date:** 2026-03-31  
**Status:** Example (calibration)  
**Brief:** _N/A — pattern reference_  
**Figma:** _[link when available]_

**Pattern references:** [Primer — Forms](https://primer.style/product/ui-patterns/forms/) (FormControl anatomy, validation timing, submit vs inline). [USWDS — Form templates](https://designsystem.digital.gov/templates/form-templates/) (accessibility: DOM order, fieldset/legend, required vs optional labeling, caution on disabled inputs).

---

## Overview

Users edit display name and public email on a single settings page. The form uses design-system form controls, validates on submit by default, and may switch to inline validation after the first failed submit. This example shows medium complexity: multiple fields, grouped radios, error summary, and explicit copy for every failure mode.

---

## Components Used

| Component | Storybook Path | Variant / Props Used | Notes |
|-----------|----------------|----------------------|-------|
| `FormField` | Forms > FormField | `label`, `helperText`, `errorMessage`, `isInvalid`, `isRequired` | Wraps each input |
| `TextInput` | Forms > TextInput | `autoComplete`, `maxLength` | Display name |
| `Select` or `TextInput` | Forms > Select / TextInput | — | Public email (product-dependent) |
| `RadioGroup` | Forms > RadioGroup | group-level validation only | Email visibility |
| `Button` | Actions > Button | `primary`, `secondary`, `isLoading` | Save, Cancel |
| `Alert` or `Banner` | Feedback > Banner | `error` or `role="alert"` | Optional top summary when ≥ 3 errors |
| `InlineMessage` | Feedback > InlineMessage | `error` | Per-field errors |

_New patterns (not in Storybook):_ None. If native browser validation is disabled, ensure custom validation is wired for screen readers (per Primer: avoid native validation UI alone).

---

## Behavior

### Profile settings form

**Default state:** Form shows labels, optional helper captions, required indicators, pre-filled values from server, Save disabled until dirty **or** Save always enabled with no-op if unchanged (pick one; below assumes Save enabled with change detection).

**Interactions:**

| User action | System response |
|-------------|----------------|
| User edits a field and blurs | No error until first submit or until field was invalid after failed submit (see validation rules) |
| User clicks Save with invalid data | Submit blocked; first invalid field focused OR interactive error summary shown when ≥ 3 errors |
| User clicks Save with valid data | Button shows loading; on success, toast "Profile saved" |
| User clicks Cancel | If dirty, confirm dialog; else navigate back |

---

## States

### Save button

| State | Trigger | Appearance | Notes |
|-------|---------|------------|-------|
| Default | Form loaded | Primary Save | |
| Loading | Save in progress | `isLoading`, disabled | Preserve width to avoid layout shift |
| Disabled | Rare: use only if product requires lock during save | Visually disabled | Prefer not to use disabled submit without explanation (USWDS: avoid disabled inputs without context; same spirit for primary actions) |

### FormField (text inputs)

| State | Trigger | Appearance | Notes |
|-------|---------|------------|-------|
| Default | Valid value | Border default, helper caption if any | |
| Error | Invalid after submit or inline pass | `isInvalid`, message below, `aria-invalid="true"` | Message tied with `aria-describedby` |
| Success (optional) | Async validation (e.g. name available) | Optional success InlineMessage | Only when extra assurance is needed (Primer) |

---

## Validation rules

**Submit-first (default):** Validate when the user attempts to save. Lets users move through the form quickly without per-keystroke interruption.

**After first failed submit:** May use inline validation on blur or change for invalid fields until fixed.

**Do not** validate before the user has finished with a field on first pass (no errors on first focus). **Do not** use placeholder as the only label (placeholders disappear and often fail contrast; screen readers do not treat placeholder as label per Primer).

**Summary banner:** If there are 3+ errors, show a `Banner` at the top listing invalid fields as anchor links; activating a link moves focus to the control. When the banner appears, focus moves to the banner container or first link per team pattern.

---

## Error States

| Error condition | User sees |
|-----------------|-----------|
| Display name empty | **Field:** "Enter a display name." |
| Display name too long | **Field:** "Use 80 characters or fewer." |
| Public email invalid format | **Field:** "Enter a valid email address." |
| Server save failed | **Banner or toast:** "Your changes couldn't be saved. Try again." |
| Session expired | **Modal or full-page:** "You're signed out. Sign in to continue." with link to sign-in |

---

## Empty States

Not applicable for this form (fields are pre-filled or blank by design). If a section depended on async options with no data, use `EmptyState` with explanation and recovery; not required for this example.

---

## Microcopy

| Element | Copy |
|---------|------|
| Page title | Profile |
| Display name label | Display name |
| Display name caption | This is how your name appears across the product. |
| Public email label | Public email |
| Visibility group legend | Who can see your email |
| Radio option | Only me / My team / Everyone (examples) |
| Save | Save changes |
| Cancel | Cancel |
| Success toast | Profile saved |
| Unsaved changes dialog title | Discard changes? |
| Unsaved changes dialog body | You have unsaved changes. If you leave, they'll be lost. |
| Discard | Discard |
| Keep editing | Keep editing |

---

## Responsive Behavior

| Breakpoint | Behavior change |
|------------|-------------------|
| Mobile (< 768px) | Single column; field order unchanged (DOM matches visual order per USWDS) |
| Desktop | Same; optional max-width on form for readability |

---

## Accessibility

- **DOM order:** Match visual order. Do not reorder fields with CSS in a way that breaks reading order for screen magnifiers or screen readers (USWDS).
- **Required fields:** Mark required fields consistently. Include a form-level line: "A red asterisk (*) indicates a required field." (Adapt to your token: asterisk or "Required" badge per design system.)
- **Optional fields:** Mark optional fields with "(optional)" in the label when most fields are required (USWDS pattern).
- **Grouping:** Use `fieldset` / `legend` (or component equivalents) for the email visibility radios so the group has one spoken label.
- **Focus order:** Logical top-to-bottom; error summary links before fields when banner is present; first invalid field focused if no summary.
- **ARIA:** Invalid inputs use `aria-invalid="true"`; error text referenced with `aria-describedby`. Remove `aria-describedby` if error node is removed from DOM (Primer).
- **Disabled inputs:** Avoid disabled text inputs for "fix later" states; prefer enabled fields with errors. If something must be disabled (e.g. irreversible system lock), provide visible explanation (USWDS).

---

## Out of Scope (v1)

- Avatar upload, password change, or SSO email restrictions.
- Inline autosave.
- Field-level success messages except where product explicitly requires async validation feedback.

---

## Open Questions

| Question | Owner | Due |
|----------|-------|-----|
| Save disabled until dirty vs always enabled? | PM + Eng | TBD |
| Email visibility: exact option set and default? | Legal / PM | TBD |

---

## Revision History

| Date | Change | Author |
|------|--------|--------|
| 2026-03-31 | Example spec for Design OS calibration | Design OS |

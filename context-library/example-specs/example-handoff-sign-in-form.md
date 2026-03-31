# UX Spec: Sign-in form — handoff-ready example

**Author:** Design OS (example)  
**Date:** 2026-03-31  
**Status:** Example (calibration)  
**Brief:** _N/A — pattern reference_  
**Figma:** _[approved frame — Sign-in / Web]_

**Pattern references:** [USWDS — Form templates](https://designsystem.digital.gov/templates/form-templates/) (sign-in template expectations, accessibility). [Primer — Forms](https://primer.style/product/ui-patterns/forms/) (labels, required semantics for simple forms, validation). This document demonstrates full annotation density for `/design-spec-draft` calibration.

---

## Overview

Web sign-in: email (or username) and password on one screen, single primary submit, links to password reset and sign-up. Login forms are the common exception where all fields are implicitly required; explicit per-field required markers may be omitted if validation on submit communicates missing fields clearly (Primer exception for patterns like login).

---

## Components Used

| Component | Storybook Path | Variant / Props Used | Notes |
|-----------|----------------|----------------------|-------|
| `PageLayout` | Layout > PageLayout | `centered`, `maxWidth="sm"` | Optional shell |
| `Heading` | Typography > Heading | `level=1` | Page title |
| `FormField` | Forms > FormField | `label`, `errorMessage`, `isInvalid` | Email and password |
| `TextInput` | Forms > TextInput | `type="email"` or `type="text"`, `autoComplete="username"` | Email |
| `TextInput` | Forms > TextInput | `type="password"`, `autoComplete="current-password"` | Password |
| `Button` | Actions > Button | `primary`, `fullWidth`, `isLoading` | Sign in |
| `Link` | Navigation > Link | inline with body text | Forgot password, Create account |
| `Alert` | Feedback > Alert | `error` | Account or server errors after submit |

_New patterns (not in Storybook):_ None.

---

## Behavior

### Sign-in page

**Default state:** Centered card or column with product logo, "Sign in" heading, email field, password field, primary "Sign in" button, forgot-password link, sign-up link. No user-specific data.

**Interactions:**

| User action | System response |
|-------------|----------------|
| User submits empty form | Inline errors on email and/or password; focus first invalid field |
| User submits wrong password | Generic error: "Email or password is incorrect." Focus first field or password per security policy |
| User submits valid credentials | Button loading; redirect to `returnUrl` or home |
| User clicks "Forgot password?" | Navigate to password reset flow |
| User clicks "Create an account" | Navigate to sign-up |

**Security / content note:** Use generic copy for auth failures when appropriate so attackers cannot distinguish valid emails from invalid (product policy).

---

## States

### Sign-in button

| State | Trigger | Appearance | Notes |
|-------|---------|------------|-------|
| Default | Ready | Primary, full width | |
| Loading | Submit sent | Spinner, `isLoading`, disabled | |
| Disabled | Only if product blocks repeat submit | Rare; prefer loading state | |

### Email field

| State | Trigger | Appearance | Notes |
|-------|---------|------------|-------|
| Default | Empty or filled | Label visible; no placeholder-as-label | Placeholder optional ("you@company.com") must not replace label |
| Error | Missing or invalid format | Error message below; `aria-invalid` | |

### Password field

| State | Trigger | Appearance | Notes |
|-------|---------|------------|-------|
| Default | — | Masked input | |
| Error | Missing or wrong | Error message below | Wrong password uses page-level or field-level message per policy |

---

## Error States

| Error condition | User sees |
|-----------------|-----------|
| Email empty | **Field:** "Enter your email address." |
| Email format invalid | **Field:** "Enter a valid email address." |
| Password empty | **Field:** "Enter your password." |
| Wrong credentials | **Alert (page):** "Email or password is incorrect." **or** field-level equivalent per policy |
| Rate limited / lockout | **Alert:** "Too many sign-in attempts. Try again in 15 minutes." |
| Server / network error | **Alert:** "Something went wrong. Try again in a few minutes." |

Avoid raw HTTP status codes in user-facing copy unless support requires it (Primer empty-state / error copy guidance).

---

## Empty States

Not applicable (form is always two inputs). Post-login destinations may use `EmptyState` patterns separately.

---

## Microcopy

| Element | Copy |
|---------|------|
| Page title (document) | Sign in |
| Heading | Sign in |
| Email label | Email |
| Email placeholder (optional) | you@company.com |
| Password label | Password |
| Primary CTA | Sign in |
| Forgot password link | Forgot password? |
| Sign-up line | Don't have an account? **Create an account** |
| Loading (button) | Signing in… |

---

## Responsive Behavior

| Breakpoint | Behavior change |
|------------|-------------------|
| Mobile (< 768px) | Full-width form; same field order; touch targets ≥ 44px |
| Tablet / Desktop | Centered column; max-width 400–480px |

---

## Accessibility

- **Focus order:** Email → Password → Sign in → Forgot password → Create account (adjust if visual order differs; DOM must match).
- **Keyboard:** Enter submits form from an input when focus is in the form (native `form` + submit button).
- **Labels:** Every input has a visible label; `placeholder` is not the sole label (Primer).
- **Errors:** Errors associated with fields via `aria-describedby`; page-level alert uses `role="alert"` or live region per component API.
- **Password:** Allow paste; do not block password managers (`autocomplete` attributes set).
- **USWDS alignment:** Simple vertical stack; validation messages visually aligned with inputs for magnifier users.

---

## Out of Scope (v1)

- SSO buttons (Google, GitHub, etc.) on the same page.
- Magic link sign-in.
- Remember this device / 2FA (separate specs).

---

## Open Questions

| Question | Owner | Due |
|----------|-------|-----|
| Exact password reset URL and sign-up URL? | PM | TBD |
| Focus target after failed login (email vs password)? | Eng + Security | TBD |

---

## Revision History

| Date | Change | Author |
|------|--------|--------|
| 2026-03-31 | Handoff-ready example for Design OS calibration | Design OS |

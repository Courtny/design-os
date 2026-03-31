# Design Principles

These are the team's guiding UX and design principles. The copilot references them when generating specs, reviewing work, and flagging inconsistencies.

Fill out the sections below with your team's actual principles. Specificity beats generality: "Reduce cognitive load by limiting primary actions to one per screen" is more useful than "Keep it simple."

---

## Core UX Principles

Replace the examples below with your team's actual principles.

### 1. [Principle Name]

**What it means:**

**In practice:**
<!--
- 
- 
-->

**Red flags (what violates this):**
<!--
-
-->

---

### 2. [Principle Name]

**What it means:**

**In practice:**

**Red flags:**

---

### 3. [Principle Name]

**What it means:**

**In practice:**

**Red flags:**

---

*(Add as many as your team has — usually 4–7 is the sweet spot.)*

---

## Accessibility Standards

**Minimum standard:** WCAG 2.1 AA (unless noted otherwise below)

**Color contrast:**
- Normal text: 4.5:1 minimum
- Large text (18px+ bold or 24px+ regular): 3:1 minimum
- UI components and focus indicators: 3:1 minimum

**Keyboard navigation:**
- All interactive elements reachable via Tab
- Focus order matches visual/reading order
- Focus indicator always visible (never hidden with `outline: none` without a replacement)
- All actions achievable without a mouse

**Screen readers:**
- All images have meaningful alt text (or `alt=""` for decorative)
- Form inputs always have associated `<label>` elements
- Error messages programmatically associated with their input
- Icons used as buttons have accessible names (`aria-label`)

**Motion:**
- Respect `prefers-reduced-motion`. No purely decorative animations required for function.

**Specific commitments or exceptions for your product:**
<!-- e.g., Mobile app: WCAG 2.1 AA. Admin portal: WCAG 2.1 A (acceptable lower standard per legal). -->

---

## Visual Language

### Typography

**Primary typeface:**
_[Fill in: e.g., Inter]_

**Scale:**
<!-- e.g., heading-xl: 32px, heading-lg: 24px, heading-md: 20px, body: 16px, small: 14px, caption: 12px -->

**Rules:**
<!-- e.g., Never go below 12px. Minimum line-height 1.4 for body text. -->

### Color

**Primary:**
_[Fill in: hex]_

**Secondary:**
_[Fill in: hex]_

**Semantic colors (use only for their semantic meaning):**
- Success:
- Warning:
- Error:
- Info:

**Rules:**
<!-- e.g., Never use raw hex values in design files — always use design tokens. -->

### Spacing

**Grid:**
<!-- e.g., 4px base unit. Spacing scale: 4, 8, 12, 16, 24, 32, 48, 64, 96. -->

**Rules:**
<!-- e.g., All spacing must use a value from the scale. Never use arbitrary values. -->

### Elevation and Shadow

<!-- e.g., Three levels: flat (no shadow), raised (card), floating (modal/popover). -->

### Motion

**Easing:**
<!-- e.g., Ease-out for entrances, ease-in for exits, ease-in-out for positional changes. -->

**Duration:**
<!-- e.g., Micro-interactions: 100ms. Transitions: 200ms. Page transitions: 300ms. Never animate longer than 400ms. -->

---

## Content and Microcopy

**Voice characteristics:**
<!-- e.g., Clear, direct, encouraging. Not cute. Not corporate. -->

**Tense:**
<!-- e.g., Present tense for UI labels and actions. -->

**Capitalization:**
<!-- e.g., Sentence case for all labels, buttons, and headings. Title case for product names only. -->

**Error messages:**
- Tell the user what went wrong
- Tell them how to fix it
- Never blame the user

**Empty states:**
- Explain why it's empty (if not obvious)
- Give users a clear next action

**Loading states:**
- Under 300ms: no indicator needed
- 300ms–1s: spinner (subtle)
- Over 1s: progress bar or skeleton screen

---

## Anti-Patterns

Patterns the team has explicitly decided not to use. Log them here so the copilot doesn't suggest them.

| Anti-pattern | Why we avoid it | Preferred alternative |
|-------------|----------------|----------------------|
| _[example: Infinite scroll in data tables]_ | Breaks keyboard navigation and "find on page" | Paginated table with page size control |
| | | |

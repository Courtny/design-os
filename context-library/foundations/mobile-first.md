# Context File: Mobile First

**Status:** Core Interaction Principle  
**Tagline:** "Design for the smallest screen first, then scale up."

---

## Executive Summary

**Mobile First** is a design strategy that starts with the most constrained context — a small touchscreen on a slow network — and progressively enhances the experience for larger screens and faster connections. It is not just a responsive CSS technique; it's a prioritization discipline. Designing for mobile first forces decisions about what truly matters, which produces better hierarchy everywhere, not just on phones.

---

## The Origin Story

Luke Wroblewski coined "Mobile First" in a 2009 article and expanded it into a book in 2011. His core argument: mobile constraints (small screen, touch input, network variability, divided attention) aren't limitations to design around — they're forcing functions that produce cleaner, more focused products. By 2023, mobile accounts for over 55% of global web traffic. Designing for desktop first and retrofitting mobile is designing for the minority first.

---

## Why It Matters for the Design OS

1. **Constraints reveal priority.** When you can only fit three things on a screen, you find out fast which three things actually matter. The answers usually improve the desktop version too.
2. **Touch is the baseline input.** A hover state, a right-click menu, or a precise cursor interaction doesn't exist on mobile. Any interaction that depends on these isn't universally accessible.
3. **Performance is a design decision.** Mobile users on cellular networks experience the product at its worst. If it's not fast on mobile, performance is a design problem — not just an engineering one.

---

## Core Principles

**Progressive Enhancement:** Start with the core feature set for mobile and add layers of complexity as screen size and capability increase. The mobile experience is the foundation, not a reduced version of the desktop.

**Content Inventory:** Every element on screen should justify its presence at mobile size. If it's not important enough to show on mobile, it may be clutter on desktop too.

**Touch Targets:** Human fingers are far less precise than mouse cursors. Interactive elements need to be large enough to tap reliably without adjacent elements interfering.

---

## Implementation Guidelines

| Concern | Guideline |
| :--- | :--- |
| **Touch target size** | Minimum 44x44px (iOS HIG) or 48x48dp (Material Design). This applies to buttons, links, checkboxes, and any tappable element. |
| **Content hierarchy** | Most critical user tasks belong at the top of the visual hierarchy. Don't make mobile users scroll to reach the primary action. |
| **Hover states** | Never rely on hover to reveal information or trigger interactions. There is no hover on touchscreens. Any functionality behind a hover needs a tap-accessible equivalent. |
| **Performance** | Mobile users are frequently on slower networks. Optimize images, defer non-critical assets, and treat load time as a design constraint, not a post-launch concern. |
| **Spacing** | Increase padding around interactive elements beyond what looks "right" on desktop. Tight spacing that works with a cursor causes tap errors on touch. |
| **Input types** | Use appropriate HTML input types (`tel`, `email`, `number`) to trigger the correct mobile keyboard. Don't make users switch keyboards manually. |

---

## Scaling Up: When Desktop Gets More

Mobile First doesn't mean desktop gets ignored — it means desktop enhancements are additive, not subtractive. Things that belong only on larger screens:

- Hover tooltips and contextual previews
- Multi-column layouts and side-by-side comparisons
- Keyboard shortcuts and power user density
- Persistent sidebars and expanded navigation

These are enhancements that take advantage of additional real estate and input precision — not features that should be retrofitted down to mobile.

---

## Warning Signs

- Designs reviewed exclusively on desktop before any mobile check
- "We'll do the mobile version later" in project planning
- Hover-only interactions for critical functionality
- Interactive elements under 44px in any dimension
- Layout that "collapses" on mobile rather than being designed for it

> **The Design OS Motto:** *If it doesn't work on mobile, it doesn't work.*

---

## Related Principles

- **Fitts's Law:** Touch target size and spacing are direct applications of Fitts's Law at mobile scale.
- **Cognitive Load:** Mobile contexts involve divided attention and time pressure. Reducing cognitive load is more important on mobile, not less.
- **Progressive Disclosure:** The primary pattern for managing feature complexity across breakpoints — show less at small sizes, reveal more as context and screen size allow.
- **Doherty Threshold:** Performance constraints on mobile make the < 400ms threshold harder to hit and more important to chase.
- **Occam's Razor:** Mobile First enforces Occam's Razor structurally — the small screen won't allow unnecessary complexity.
- **Cotten's Many Doors:** Mobile changes how door types can work. Hover-triggered Side-Doors don't exist on touch — any contextual entry point needs a tap-accessible equivalent. The Grand Entrance requirements also tighten: with no persistent sidebar or hover state to fall back on, the primary path must be unambiguous and in a conventionally expected location.

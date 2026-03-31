# Semantic Color

Color in UI is not decoration. It's communication. Semantic color means assigning specific, consistent meanings to colors across your entire product, then enforcing those meanings everywhere.

---

## The Core Idea

Users learn your color language whether you teach it intentionally or not. If red means "error" in your form validation but also means "sale price" in your product cards, you've taught users that red means two different things. Their brain has to resolve the ambiguity every time, which adds cognitive load and erodes trust in the visual system.

Semantic color is the practice of making color meaningful and consistent:
- **Error/danger** always uses the same red. Nothing else uses that red.
- **Success/confirmation** always uses the same green. Nothing else uses that green.
- **Warning/caution** always uses the same amber. Nothing else uses that amber.
- **Info/neutral emphasis** always uses the same blue. Nothing else uses that blue.
- **Interactive elements** (links, buttons, focus rings) use a consistent color that signals "you can act on this."

When a color carries the same meaning everywhere, users stop reading and start recognizing. That's faster, less effortful, and more accessible.

---

## Why It Matters

### Reduced cognitive load
When red always means the same thing, users don't have to interpret it. They react. This is especially important in high-stress contexts like error recovery, form validation, and destructive actions.

### Accessibility
WCAG 1.4.1 (Use of Color) requires that color is never the sole means of conveying information. But even beyond compliance, semantic consistency helps users with color vision deficiencies: if error red is always paired with an error icon and error text, the system is resilient even when the red isn't perceived.

### Scalability
Products grow. New features, new surfaces, new designers. A defined semantic color system means new work inherits the right colors automatically. Without it, every new screen introduces color drift.

### Dark mode and theming
If colors are defined semantically (token: `color-error`, `color-success`) rather than as absolute values (hex: `#EF4444`), they can remap across themes without manual rework.

---

## The Layers of Color in UI

Most color systems have three layers. Problems happen when the layers bleed into each other.

### 1. Brand colors
The product's identity. Primary brand color, secondary, accents. These appear in headers, marketing surfaces, logos, and brand-heavy moments.

### 2. Semantic colors
Functional colors that carry specific meaning. Error, success, warning, info. These never change meaning across the product.

### 3. Neutral/structural colors
Backgrounds, borders, dividers, disabled states, text colors. These create the spatial structure of the interface and don't carry semantic meaning on their own.

**The danger zone:** When brand colors overlap with semantic colors. If your brand is green and your success state is also green, you've created ambiguity. Users can't tell whether green means "our brand" or "this worked." The fix is usually to shift one or the other slightly, or to pair the semantic use with a secondary indicator (icon, text, border).

---

## Common Anti-Patterns

### Red for emphasis (not error)
Using the error color to draw attention to non-error content: sale prices, urgency labels, "hot" indicators. This trains users to feel anxiety when they see red, even in safe contexts, and dilutes the error signal when it matters.

### Green for branding (when it also means success)
If your brand green and your success green are the same, every brand-colored element implicitly says "this is good/done/confirmed." Users learn to ignore the signal.

### Blue for everything
Interactive blue (links, buttons) and informational blue (info banners, tooltips) are often the same color. This is usually fine, but check whether non-interactive blue elements look clickable. If users click on info text expecting it to be a link, the blue is doing double duty.

### Color-only state indicators
Status badges, progress indicators, or form validation that uses color as the only differentiator. Remove the color and ask: can a user still tell what's happening? If not, add a label, icon, or pattern.

### Inconsistent semantic mapping
Error is `#EF4444` on the settings page but `#DC2626` on the checkout page. Both are "red," but they're different reds. This makes the system feel unreliable, even if users can't articulate why.

### Decorative use of semantic colors
Using semantic colors (red, green, amber) for decorative or branding purposes in charts, illustrations, or marketing sections. Even in non-UI contexts, these colors carry their learned meaning.

---

## Applying Semantic Color in Practice

### Define your tokens
In `principles.md`, fill out the semantic color section with exact values:
- Success: [hex]
- Warning: [hex]
- Error: [hex]
- Info: [hex]
- Interactive: [hex]

These are the source of truth. Every use of these colors in the product should trace back to these tokens.

### Audit existing usage
Look at every screen and ask: for each color that isn't a neutral, what does it mean? If you can't answer in one word (error, success, link, warning), the color might be decorative or ambiguous.

### Pair color with a secondary indicator
For every semantic color: what else communicates the same thing? An icon, a label, a border, a position change. Color should reinforce meaning, not carry it alone.

### Test by removing color
Desaturate the screen. Can users still complete every task? Can they still identify errors, successes, and interactive elements? If not, the design depends too heavily on color.

### Watch for brand collisions
Map your brand palette against your semantic palette. Where they overlap, decide which one shifts. Usually the brand use can tolerate a slight hue or saturation change more easily than the semantic use.

---

## Related Concepts

- **WCAG 1.4.1 (Use of Color):** Color cannot be the sole means of conveying information. See `wcag.md`.
- **Von Restorff Effect:** Distinctive elements are remembered. Semantic color leverages this by making important states visually distinct. See `von-restorff-effect.md`.
- **Cognitive Load:** Consistent color reduces interpretation effort. See `cognitive-load.md`.
- **Design Tokens:** The implementation mechanism for semantic color in code and design tools.

---

## Quick Reference

| Layer | Purpose | Changes across themes? | Examples |
|-------|---------|----------------------|----------|
| Brand | Identity | Usually not | Logo, header, marketing accents |
| Semantic | Meaning | Values change, meaning stays | Error, success, warning, info, interactive |
| Neutral | Structure | Values change | Backgrounds, borders, text, disabled states |

**Rule of thumb:** If you can't name what a color means in one word, it's either neutral (fine) or ambiguous (fix it).

# Refactoring UI: Product Design Principles Reference

This document structures core product design principles from *Refactoring UI* into a categorized reference guide. Use it for design decisions, specs, critiques, and copilot context when craft or visual hierarchy questions come up.

---

## 1. Workflow & strategy

- **Feature-first design**: Start designing with actual functionality rather than the app "shell" (navigation bars, sidebars). An app is a collection of features; designing them first gives the context needed for layout and navigation.
- **Detail deferral**: Avoid low-level decisions (specific typefaces, shadows, icons) early. Use disposable sketches or thick markers (e.g. Sharpies) to focus on layout and ignore distracting details.
- **Grayscale-first design**: Resist color immediately. Designing in grayscale forces spacing, contrast, and size to establish hierarchy.
- **Iterative design cycles**: Work in short cycles: design a simple version of a feature, build it, iterate on the real interface instead of imagining every edge case up front.
- **Pessimistic shipping**: Design the smallest useful version you can ship. Avoid implying functionality you are not ready to build so the product stays shippable.

---

## 2. Visual hierarchy & data

- **Hierarchy priority**: Use visual hierarchy to signal importance relative to other elements. Highlight what matters; de-emphasize secondary information so the interface feels intentional.
- **Hierarchy tools**: Do not rely only on font size. Use weight (e.g. bold for primary) or softer colors for supporting text to show importance without hurting readability.
- **Label management**: Treat labels as a last resort. Use data format (email, currency) and context so information is self-explanatory. If labels are needed, de-emphasize them so the data stays the focus.
- **Balance weight and contrast**: Large-surface elements (bold text, solid icons) feel heavier. Balance with lower contrast or softer colors.
- **Action hierarchy**: Group actions as primary (high contrast), secondary (outline or low contrast), and tertiary (link-style) to guide users without a busy UI.

---

## 3. Layout & spacing systems

- **White space strategy**: Start with more white space than you think you need, then remove incrementally until it feels right, instead of adding space only when things look cramped.
- **Non-linear systems**: Use a fixed spacing/sizing scale (e.g. 16px base with steps like 4, 8, 12, 16, 24, 32). Small changes at the low end matter more than at the high end.
- **Content-driven widths**: You do not need to fill the screen. Give forms, sidebars, and similar blocks a fixed width suited to content instead of fluid percentages that scale awkwardly.
- **Proximity and connection**: Use spacing to group related elements. Keep more space *between* groups than *within* groups so relationships stay clear.

---

## 4. Typography & color systems

- **Hand-crafted type scales**: Pick a small set of font sizes for consistency and faster decisions. Avoid defining scales only with relative `em` units; nesting makes computed sizes inconsistent.
- **Proportional line-height**: Line-height and line length go together; wider content often needs taller line-height (up to about 2.0) so the eye finds the next line. Large display type often needs *shorter* line-height relative to size.
- **Pre-defined color shades**: Define roughly 8–10 shades per color up front. For primary/accent, pick a base that works on buttons and build lighter/darker steps from there.
- **Perceived brightness**: When lightening or darkening, nudge hue toward bright (yellow/cyan) or dark (blue/red) so shades stay vivid and less muddy or washed out.

---

## 5. UI components & finishing

- **Depth and elevation**: Treat light as coming from above so elements read as raised or inset. Use shadows to show elevation; larger, softer shadows tend to draw more attention.
- **Image contrast**: Text on images needs readable contrast: overlays, reduced image contrast, or subtle text shadows so type stays legible.
- **Border alternatives**: Separate regions with alternate backgrounds, soft shadows, or extra spacing instead of piling on borders.
- **Component flexibility**: Standard patterns are starting points. Tables can merge columns for hierarchy; radios can become selectable cards when it helps the task.

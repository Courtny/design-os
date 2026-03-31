# Card — Component UX Guidance

**Storybook:** `Layout > Card`
**Figma:** _(add your Figma component link)_

---

## When to Use

Use `Card` to present a collection of related content summaries where each card acts as an entry point to more detail. Cards work best as members of a group, not in isolation.

A card should be self-contained and modular. You should be able to rearrange cards in a collection without breaking the meaning of any individual card.

---

## Variants

| Variant | When to use |
|---------|-------------|
| `default` | Standard card with header, body, and optional footer. Use for most content collections. |
| `clickable` | The entire card surface is a click/tap target. Use when the card links to a detail view. |
| `with-header` | Card with a prominent header element, like an image or media, above the body content. |

---

## Do

- Make cards actionable. Every card should link to more detailed content or trigger an action.
- Use a consistent structure across cards in the same group. Same content types, same layout.
- Include non-redundant content. Each card in a collection should be distinguishable by its content, not just its position.
- Use the grid system to control card width. Cards should adapt to the layout grid, not have fixed widths.
- Keep body text short. A card is a summary, not a full article.
- Use proper image sizing. Card images resize across breakpoints. Test that images work at all sizes.

---

## Avoid

- Avoid using cards as a substitute for table rows. If the data is structured and comparable, use `DataTable`.
- Avoid cards for sequential, continuous text. If users are meant to read from card to card in order, use headings and body text instead.
- Avoid decorative-only cards. Don't wrap content in a card just to put a border around it. The card component is for card patterns.
- Avoid repeating the same image across every card in a collection. Repeated visuals make cards harder to distinguish.
- Avoid skeumorphic card styling (paper textures, folds, bent corners). Keep it simple.

---

## States

| State | Trigger | Notes |
|-------|---------|-------|
| Default | Initial render | Card visible with content. |
| Hover | Mouse over clickable card (desktop) | Subtle elevation change or border highlight. Entire card surface should indicate interactivity. |
| Focus | Keyboard focus on clickable card | Visible focus ring on the card or its primary link. |
| Active | Click/tap in progress | Brief pressed feedback. |
| Loading | Content not yet available | Skeleton card with placeholder shapes for header, body, and image. |

---

## Accessibility

- Use `<ul>` for card groups and `<li>` for each card. This lets screen readers enumerate items and provides shortcut navigation between cards.
- Use the correct heading level for card titles. Card headings must fit the logical document outline, not always be `<h3>`.
- For clickable cards, the click target should be the card's primary link, not a wrapper `<div>` with an `onClick`. Use a real `<a>` element.
- If the card has a media element and a header, keep the header before the media in the DOM even if CSS displays it differently. Logical reading order matters.
- Images in cards need meaningful `alt` text. If the image is purely decorative and the card title conveys the meaning, use `alt=""`.

---

## Pairings

- `Card` group + layout grid — control card sizing with grid columns (`grid-col-4` for three-up, etc.)
- `Card (clickable)` + `Badge` — status indicators on card content
- `Card (with-header)` + image — media-rich content previews
- `Card` + `Button` in footer — explicit call-to-action per card

---

## Common Mistakes

- Making the entire card clickable but also having separate interactive elements (buttons, links) inside the card. Click targets overlap and confuse users. Pick one: the whole card is the target, or specific elements within it are.
- Inconsistent card heights in a row. Use CSS flex stretch (the default) so all cards in a row align top and bottom.
- Putting too much content in a card. If you're writing multiple paragraphs or bullet lists in the body, it's not a card anymore. Put that content on its own page.
- Using cards for a single item. Cards are for collections. A standalone piece of content is better as an `aside`, a callout, or just page content.

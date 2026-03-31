# DataTable — Component UX Guidance

**Storybook:** `Data > DataTable`
**Figma:** _(add your Figma component link)_

---

## When to Use

Use `DataTable` to display structured, tabular data that users need to scan, compare, or act on. Tables work best when the data has a consistent structure across rows and the user benefits from seeing multiple items at once.

**Not for layout.** Never use a table to control page layout. Tables are for data.

---

## Variants

| Variant | When to use |
|---------|-------------|
| `basic` | Read-only data display. No interaction beyond scrolling. |
| `sortable` | Users need to reorder rows by column values (alphabetical, numerical, date). |
| `selectable` | Users need to select one or more rows for bulk actions (delete, export, assign). |
| `paginated` | Data set is large enough that showing all rows at once would hurt performance or readability. |

Variants can be combined: a table can be sortable, selectable, and paginated at the same time.

---

## Do

- Always include a header row with clear, short column labels.
- Right-align numerical data (currency, counts, percentages) so decimal points line up visually.
- Use a monospace font for dense numerical columns to improve scannability.
- Keep formatting consistent within a column. If most values are in days, don't switch to weeks for some rows.
- Add a `<caption>` or visible title so users (and screen readers) know what the table contains.
- Use striped rows for tables with many rows to help the eye track across.
- Provide a sticky header for long tables so column labels stay visible while scrolling.
- Enable sort only on columns where it's useful. Not every column needs sorting.

---

## Avoid

- Avoid cramming too many columns. If users have to scroll horizontally on desktop, consider which columns are truly necessary.
- Avoid long paragraphs in table cells. Cell content should be brief and scannable.
- Avoid using tables for content that doesn't have a consistent structure across rows. Use cards or lists instead.
- Avoid sorting on tables with merged cells (`colspan` or `rowspan`). Sort logic breaks.

---

## States

| State | Trigger | Notes |
|-------|---------|-------|
| Default | Data loaded | Rows visible with header. |
| Loading | Data fetching | Show skeleton rows or a spinner. Keep header visible. |
| Empty | Zero results or no data | Use `EmptyState` component inside the table container. Always include a next action. |
| Error | Data fetch failed | Show error message with retry action. Don't show an empty table. |
| Sorted | User clicks sortable column header | Sort indicator visible on active column. Announce sort change to screen readers. |
| Row selected | User checks row checkbox | Visual highlight on selected rows. Bulk action bar appears. |
| Row hover | Mouse over a row (desktop) | Subtle background change for clickable rows only. |

---

## Responsive Behavior

- **Scrollable:** For data-dense tables, wrap in a horizontally scrollable container. Add `tabindex="0"` to the scroll container so keyboard users can scroll it.
- **Stacked:** For text-heavy tables (directories, content lists), stack cells vertically on mobile. Each cell should display its column header as a label using `data-label` or equivalent.
- **Sticky header:** Not compatible with the stacked variant. Use one or the other.

---

## Accessibility

- Use `<th scope="col">` for column headers and `<th scope="row">` for row headers.
- For complex tables with multiple header levels, use `id` on each header and `headers` on each data cell.
- Add a `<caption>` element inside the `<table>` for the table title. It can be visually hidden but must be present for screen readers.
- Sortable columns: include an `aria-live="polite"` region that announces sort state changes. Don't manually add `aria-label` to sort buttons; let the component handle it.
- Scrollable containers must have `tabindex="0"` so keyboard users can scroll.
- Selectable rows: checkboxes must have accessible labels (e.g., "Select [row name]").

---

## Pairings

- `DataTable (paginated)` + `Pagination` — standard pattern for large data sets
- `DataTable (selectable)` + `Button` bulk action bar — actions on selected rows
- `DataTable (empty)` + `EmptyState` — always use `EmptyState` for zero results, never a blank table
- `DataTable` + `Badge` — status indicators within table cells

---

## Common Mistakes

- Showing a completely blank table when there's no data. Always use the `EmptyState` component.
- Forgetting overflow behavior for long text in cells. Define whether cells truncate, wrap, or show a tooltip.
- Missing loading state. If data is async, users see a flash of empty content before rows appear.
- Sort icons that don't update. The active sort column and direction should always be visually indicated.
- Forgetting `tabindex="0"` on scrollable table containers. Keyboard users can't scroll without it.

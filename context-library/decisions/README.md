# Design Decisions

Design Architecture Decision Records (ADRs) and decision logs. The copilot checks here before suggesting patterns — if a question was already decided, it won't re-open it.

---

## What Belongs Here

- **Pattern decisions:** Why the team chose one UI pattern over another
- **Design system ADRs:** Why a component was built a certain way, what alternatives were rejected
- **Process decisions:** Changes to critique structure, handoff process, or tooling
- **Trade-off logs:** Where the team made a deliberate trade-off (e.g., accessibility vs. deadline)

---

## File Naming

`[topic]-[date].md`

Examples:
- `filter-pattern-selection-2025-02.md`
- `mobile-navigation-model-2024-11.md`
- `empty-state-standardization-2025-01.md`

---

## File Format

Use `templates/decision-log-template.md` as the base structure. At minimum, document:
1. What was decided
2. Why (the key driver)
3. What alternatives were rejected and why
4. Any known trade-offs

---

## Why This Matters

Design decisions get re-litigated constantly. Logging them stops the team from having the same conversation six months later. The copilot also uses these to give context-aware suggestions ("we already considered X and rejected it because...").

# Nielsen's 10 Usability Heuristics

> General principles for interaction design used as a checklist for usability evaluation.

---

## The 10 Heuristics

1. **Visibility of System Status** — Keep users informed about what is going on, through appropriate feedback within reasonable time.
2. **Match Between System and Real World** — Use words, phrases, and concepts familiar to the user, not internal jargon. Follow real-world conventions.
3. **User Control and Freedom** — Users often choose system functions by mistake. Provide a clear "emergency exit" (undo/redo) without requiring extended dialogue.
4. **Consistency and Standards** — Follow platform and industry conventions. Users shouldn't have to wonder whether different words, situations, or actions mean the same thing.
5. **Error Prevention** — Design to prevent problems from occurring in the first place. Eliminate error-prone conditions or check for them and confirm before proceeding.
6. **Recognition Rather Than Recall** — Make objects, actions, and options visible. Don't make users remember information from one part of the interface to another.
7. **Flexibility and Efficiency of Use** — Provide shortcuts for expert users. Allow users to tailor frequent actions. Accelerators should be invisible to novices but available to power users.
8. **Aesthetic and Minimalist Design** — Don't show irrelevant or rarely needed information. Every extra unit of information competes with relevant information and diminishes its visibility.
9. **Help Users Recognize, Diagnose, and Recover from Errors** — Error messages should be in plain language, clearly indicate the problem, and constructively suggest a solution.
10. **Help and Documentation** — Even better if the system doesn't need documentation, but if necessary, it should be easy to search and focused on the user's task.

---

## Using These in Practice

These are most useful as a **heuristic evaluation checklist** — go through each one against a flow or prototype and note violations. Works well during critique prep or before a handoff review.

- **Specs:** Flag which heuristics a new pattern is designed to address.
- **Critique:** Use as structured feedback categories ("this violates H8 — there's too much competing information here").
- **Error states:** H9 is often the most neglected. Default error messages from engineering almost never meet it.
- **New patterns:** H4 (consistency) and H6 (recognition) are the first two to check before proposing something non-standard.

---

## Related Foundations

- [`affordance.md`](affordance.md) — closely tied to H6 (recognition) and H3 (user control)
- [`aesthetic-usability-effect.md`](aesthetic-usability-effect.md) — relevant to H8 (aesthetic and minimalist design)
- [`mental-models.md`](mental-models.md) — directly informs H2 and H4
- [`cottens-many-doors.md`](cottens-many-doors.md) — Many Doors maps directly onto H6 (Side-Doors and Safety Nets show options at the moment of need, reducing recall burden), H7 (the Shortcut door type is the accelerator pattern for power users), and H3 (multiple entry points give users agency over how they reach their goal)

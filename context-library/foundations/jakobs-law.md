# Jakob's Law

> Users spend most of their time on other sites. This means users prefer your site to work the same way as all the other sites they already know.

Coined by Jakob Nielsen. The implication is that users arrive at your product with a fully formed set of expectations built from every other app they've ever used. Breaking those expectations has a real cost: users have to stop and learn instead of just doing.

---

## Core Principles

**Mental Consistency** — Users transfer expectations from familiar products to yours. A shopping cart icon should open a cart. A hamburger menu should open navigation. These aren't design choices; they're conventions users already know.

**Lower Learning Curve** — By following conventions, you allow users to focus on their goals rather than learning the UI. Novel UI patterns are a tax on every user who encounters them.

---

## Application

1. **Use standard icons for universal actions** — Magnifying glass for search, envelope for email, bell for notifications. Don't reinvent these.
2. **Place common elements in expected locations** — Logo top-left, account/profile top-right, primary nav top or left. Users scan from muscle memory first.
3. **Only break conventions if the new solution provides significantly higher value** — The burden of proof is high. If a new pattern tests 10-15% better in usability testing, that might justify the learning cost. "It's more creative" doesn't.

---

## When to Override

Sometimes conventions are worth breaking:

- The convention actively harms your users (e.g., a dark pattern that's become "standard").
- Your product category is new enough that no convention exists yet.
- Your research shows your users have a different mental model than the general population (domain-specific tools, professional software).

In these cases, document the decision in `context-library/decisions/` and note the research or rationale behind it.

---

## The Tradeoff with Innovation

Jakob's Law can become an excuse for no-growth conservatism. The counterpoint: if every product followed conventions rigidly, nothing would ever improve. The useful framing is **progressive deviation** — start conventional, earn user trust, then introduce the new pattern gradually with clear affordances.

---

## Related Foundations

- [`mental-models.md`](mental-models.md) — Jakob's Law is mental model theory applied at a product-ecosystem level
- [`nielsens-heuristics.md`](nielsens-heuristics.md) — H4 (consistency and standards) is the heuristic expression of this law
- [`affordance.md`](affordance.md) — Conventional affordances work because of Jakob's Law: users already know what they do
- [`cottens-many-doors.md`](cottens-many-doors.md) — The Grand Entrance rule depends on Jakob's Law: the primary entry point must live where users already expect to find it, based on every other product they've used

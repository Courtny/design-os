# Design Foundations

This folder holds **durable reference knowledge** that informs design judgment: HCI concepts, interaction theory, visual craft references, and prioritization frameworks.

These are not team process docs (see `../methodology/`) and they're not your team's committed rules (see `../design-system/principles.md`). They're the "why behind the how" — concepts you reach for when making decisions, writing specs, or grounding a critique.

The copilot checks here for concept and theory questions: "What is affordance?", "Why does aesthetics affect perceived usability?", "How should we prioritize this sprint?"

---

## What Belongs Here

- **Interaction and perception:** HCI concepts, cognitive effects, and psychological principles that explain how users read and act on UI
- **Visual craft:** Condensed references from established design books or frameworks your team uses
- **Prioritization and scope:** Decision lenses for choosing what to build, refine, or cut

---

## Contents

### Attention and Memory

- [`selective-attention.md`](selective-attention.md) — Selective attention: users see what they're looking for, banner blindness, attention path vs. spatial visibility
- [`serial-position-effect.md`](serial-position-effect.md) — Serial position effect: primacy and recency, placement strategy for nav, lists, and CTAs
- [`working-memory.md`](working-memory.md) — Working memory: active task context, recognition over recall, persistence across steps
- [`millers-law.md`](millers-law.md) — Miller's Law: working memory limits (7 ± 2), chunking strategies, what the law doesn't mean
- [`chunking.md`](chunking.md) — Chunking: grouping information into meaningful units, form sections, card patterns, scannability
- [`zeigarnik-effect.md`](zeigarnik-effect.md) — Zeigarnik Effect: incomplete tasks stay mentally active, re-engagement pull, open loop management
- [`von-restorff-effect.md`](von-restorff-effect.md) — Von Restorff Effect: distinctiveness drives attention and memory, primary CTAs, error states, badge notifications

### Perception and Visual Organization

- [`gestalt-principles.md`](gestalt-principles.md) — Gestalt: proximity, similarity, closure, continuity; visual grouping rules and when conventions break down
- [`law-of-proximity.md`](law-of-proximity.md) — Law of Proximity: near means related, spacing as communication, 2:1 heading ratio
- [`law-of-similarity.md`](law-of-similarity.md) — Law of Similarity: similar elements imply same category, visual consistency as functional promise
- [`law-of-common-region.md`](law-of-common-region.md) — Law of Common Region: enclosure groups elements, cards, form sections, background fills
- [`law-of-uniform-connectedness.md`](law-of-uniform-connectedness.md) — Law of Uniform Connectedness: visual links signal relationships, progress steps, breadcrumbs, tabs
- [`law-of-pragnanz.md`](law-of-pragnanz.md) — Law of Prägnanz: brain defaults to simplest interpretation, icon ambiguity, layout clarity
- [`affordance.md`](affordance.md) — Affordance (Gibson, Norman): perceived vs. latent action possibilities, signifiers, false/hidden/negative affordances, implementation table

### Cognitive Load and Decision-Making

- [`cognitive-load.md`](cognitive-load.md) — Cognitive load: intrinsic vs. extraneous vs. germane load, how to spot overload, reduction strategies
- [`cognitive-bias.md`](cognitive-bias.md) — Cognitive bias: anchoring, loss aversion, status quo bias, framing — ethical design applications
- [`hicks-law.md`](hicks-law.md) — Hick's Law: decision time vs. choice count, progressive disclosure, defaults and recommendations
- [`choice-overload.md`](choice-overload.md) — Choice Overload: paradox of choice, decision abandonment, progressive disclosure, smart defaults
- [`mental-models.md`](mental-models.md) — Mental models: expectation vs. reality, interface mapping, common mismatches to watch for
- [`occams-razor.md`](occams-razor.md) — Occam's Razor: simplest sufficient solution wins, feature addition cost, complexity removal discipline

### Interaction and Behavior

- [`fitts-law.md`](fitts-law.md) — Fitts's Law: target size and distance trade-offs, touch targets, screen edges, accessibility connection
- [`mobile-first.md`](mobile-first.md) — Mobile First: progressive enhancement, touch target sizing, no-hover rule, performance as a design constraint, scaling up to desktop
- [`doherty-threshold.md`](doherty-threshold.md) — Doherty Threshold: < 400ms response for flow preservation, perceived performance, skeleton screens
- [`flow.md`](flow.md) — Flow: conditions for deep engagement, interruption cost, challenge-skill balance, flow destroyers
- [`goal-gradient-effect.md`](goal-gradient-effect.md) — Goal-Gradient Effect: motivation increases near the finish line, progress indicators, completion anxiety
- [`peak-end-rule.md`](peak-end-rule.md) — Peak-End Rule: memory shaped by worst moment and final moment, success state design, error recovery
- [`paradox-of-active-user.md`](paradox-of-active-user.md) — Paradox of the Active User: nobody reads instructions, contextual help, forgiving forms, recovery-first design
- [`postels-law.md`](postels-law.md) — Postel's Law: accept flexible input formats, conservative output, form tolerance

### Usability Standards

- [`nielsens-heuristics.md`](nielsens-heuristics.md) — Nielsen's 10 heuristics: usability evaluation checklist, practical application per heuristic, cross-references
- [`jakobs-law.md`](jakobs-law.md) — Jakob's Law: user expectations shaped by other products, when to follow vs. break conventions
- [`aesthetic-usability-effect.md`](aesthetic-usability-effect.md) — Aesthetic-usability effect (Kurosu & Kashimura): perceived usability vs. actual usability, halo and forgiveness, implementation rules
- [`teslars-law.md`](teslars-law.md) — Tesler's Law: complexity is conserved, smart defaults, progressive disclosure, honest complexity limits
- [`parkinsons-law.md`](parkinsons-law.md) — Parkinson's Law: work expands to fill available space, input sizing, character limits, constraints as guidance
- [`wcag.md`](wcag.md) — WCAG (W3C): POUR principles, contrast ratios, alt text, keyboard navigation, focus states, color independence

### Visual Craft

- [`refactoring-ui-principles.md`](refactoring-ui-principles.md) — Condensed *Refactoring UI* reference: feature-first workflow, visual hierarchy, spacing systems, typography, component patterns
- [`semantic-color.md`](semantic-color.md) — Semantic color: assigning consistent meaning to colors, brand vs. semantic vs. neutral layers, common anti-patterns, token adherence, WCAG 1.4.1 connection
- [`tufte-principles.md`](tufte-principles.md) — Tufte (*VDQI*): graphical excellence and integrity, data-ink ratio, chartjunk, small multiples, data density, Tufte test for charts and dashboards

### Prioritization and Scope

- [`80-20-framework.md`](80-20-framework.md) — Pareto-based prioritization: critical path UX, high-leverage systems, product scope, decision matrix, anti-patterns

---

### Original Principles

- [`cottens-many-doors.md`](cottens-many-doors.md) — Cotten's Many Doors (Courtny Cotten): redundant entry points by type (Grand Entrance, Shortcut, Side-Door, Safety Net), Entry Point Matrix, visual weighting rules, Funhouse anti-patterns

---

## Suggested Additions

Drop any concept or theory reference your team finds useful.

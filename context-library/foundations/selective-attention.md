# Context File: Selective Attention

**Status:** Core Interaction Principle  
**Tagline:** "Users see what they're looking for. Everything else is wallpaper."

---

## Executive Summary

**Selective attention** is the cognitive process of focusing on a subset of available stimuli while ignoring the rest. Users don't process everything on a screen — they scan for what's relevant to their current goal and actively filter out everything else. This has a critical design implication: elements that aren't aligned with the user's current task are invisible, no matter how visually prominent they are. Placement, timing, and task alignment matter as much as size and color.

---

## Background

Selective attention is a foundational concept in cognitive psychology, demonstrated most famously by the "invisible gorilla" experiment (Simons and Chabris, 1999): participants asked to count basketball passes frequently failed to notice a person in a gorilla suit walking through the scene. Attention is a resource, and when it's directed toward a task, it filters out the irrelevant — even the visually obvious.

---

## Why It Matters for the Design OS

1. **Banner blindness is selective attention.** Users learn to ignore UI zones that consistently contain ads or promotional content. Once they've categorized a region as irrelevant, they stop seeing it — permanently, for that context.
2. **Important information placed "above the fold" isn't automatically seen.** If it's not on the user's task path, it won't be noticed. Error messages, warnings, and status indicators must be positioned on the path of attention, not just in a visible location.
3. **Attention is sequential, not spatial.** Users flow through a task; they don't survey the whole screen first. This means what's visible at the moment of a specific action matters far more than overall page visibility.

---

## Implementation Guidelines

| Strategy | Application |
| :--- | :--- |
| **Put critical info on the task path** | Error messages should appear adjacent to the field in error, not in a banner at the top of the page. Confirmation prompts should appear where the user just acted. |
| **Use motion to recapture attention** | Animation is one of the few attention-capture mechanisms that works against selective filtering. Use it sparingly for genuinely important state changes. |
| **Don't hide important features in ignored zones** | If a feature lives in a sidebar or header area that users typically scan as navigation, they may never discover it even if it's in plain sight. |
| **Time alerts to task context** | A promotion shown mid-task will be ignored or resented. The same information shown at task completion has a much higher chance of being processed. |
| **Reduce noise to increase signal** | The more visual competition on a page, the harder users must work to find what they're looking for — and the more they selectively filter. Fewer elements means better attention on what matters. |

---

## Selective Attention and Accessibility

Screen readers and keyboard users interact sequentially — they process content in order, not by scanning spatially. Designing with selective attention in mind often aligns with good accessibility: put important information close to the action it relates to, don't rely on spatial positioning alone, and ensure logical reading order matches visual order.

> **The Design OS Motto:** *Don't just put it where users can see it. Put it where they're already looking.*

---

## Related Principles

- **Von Restorff Effect:** What's visually different captures attention despite selective filtering.
- **Cognitive Load:** High cognitive load narrows selective attention further — users under load see even less.
- **Serial Position Effect:** Users pay more attention to the first and last items in a list, partly because their attention is still fresh (first) or re-engaged (last).
- **Law of Prägnanz:** Users focus attention on the simplest interpretation of what's in their task path.
- **Cotten's Many Doors:** The Contextual Side-Door and Safety Net door types work because they appear precisely where the user's attention already is — not in a globally visible location, but on the task path at the moment of need.

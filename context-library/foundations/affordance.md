# Context File: Affordance

**Status:** Core Interaction Principle  
**Tagline:** "Don't make them think; just make them act."

---

## Executive Summary

**Affordance** is the relationship between a physical or digital object and a person. It is the property of an object that defines its possible uses or makes clear how it can or should be used. When a design has strong affordances, the user instinctively knows how to interact with it without instructions or labels.

## The Evolution of the Concept

- **James J. Gibson (1977):** A psychologist who coined the term to describe all "action possibilities" latent in an environment, independent of the individual's ability to see them.
- **Don Norman (1988):** In *The Design of Everyday Things*, Norman adapted the term for design. He focused on **perceived affordances**—what the user *thinks* they can do based on visual cues.

---

## Why It Matters for the Design OS

In our system, affordances are the "visual language of capability." They ensure that the interface is intuitive and accessible.

1. **Reduced Cognitive Load:** Users shouldn't have to "solve" your UI. A button should look like a button, and a slider should look like it can be moved.
2. **Immediate Discoverability:** Strong affordances allow users to explore a new interface with confidence, knowing that their guesses about how things work will likely be correct.
3. **Error Prevention:** By providing clear cues, we prevent "false affordances" where a user tries to interact with a non-interactive element (and gets frustrated).

---

## Implementation Guidelines

| Type | Definition | Design OS Application |
| :--- | :--- | :--- |
| **Physical Affordance** | Cues from the physical world (texture, shape). | Use shadows (elevation) and gradients to mimic physical depth in digital buttons. |
| **Hidden Affordance** | An action that is available but has no visual cue. | Use "pull-to-refresh" or "swipe-to-delete" only for power users; always provide a visible alternative. |
| **False Affordance** | An element looks interactive but isn't. | **Avoid** blue underlined text for non-links or grayed-out boxes that look like disabled buttons. |
| **Negative Affordance** | A cue that indicates an action is *not* possible. | Use "disabled" states (low contrast, no shadow) for buttons that cannot be clicked yet. |

---

## The Secret Ingredient: Signifiers

Don Norman later clarified that what designers often call "affordances" are actually **signifiers**.

- The **affordance** is the *possibility* of the action (a screen can be touched).
- The **signifier** is the *signal* that tells you where and how (a "Buy Now" button with a drop shadow).

In the Design OS, we treat signifiers as the "braille" of the UI—they guide the user's hand before they even realize they are making a choice.

> **The Design OS Motto:** *If a user has to ask "Can I click this?", the design has already failed.*

---

## Related Principles

- **Mental Models:** Users bring expectations from other apps; don't break them (e.g., a floppy disk icon means "Save").
- **Mapping:** The logical relationship between a control and its effect (e.g., turning a knob clockwise to increase volume).
- **Feedback:** The immediate confirmation that an affordance was successfully acted upon (e.g., a button changing color when pressed).
- **Cotten's Many Doors:** Every door type must have clear affordance — it must look interactive, be labeled consistently, and be visually distinct from surrounding content. A Side-Door or Safety Net that doesn't read as actionable is a door with no handle.

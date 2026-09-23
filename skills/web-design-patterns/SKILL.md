---
name: web-design-patterns
description: Choose website layout and motion techniques that fit the audience, visual register, and user task, using a compact library of implementation approaches and contexts where each technique backfires.
---

# Web design patterns

Choose the effect after you understand the job the page must do.

A booking page, a reading interface, and an immersive portfolio can all be
well designed. They should not borrow the same interaction merely because
it looks impressive in a demo.

## Make two decisions

**Audience and task:** What must visitors understand, trust, or do? Name the
primary action and the conditions in which it must work, including touch,
keyboard, slower devices, and reduced motion.

**Visual register:** What should the experience feel like?

| Register | Main tools | Common failure |
|---|---|---|
| Editorial minimal | Type, grid, space, deliberate pacing | Empty composition without hierarchy |
| Brutalist | Raw typography, strong contrast, direct expression | Unclear navigation |
| Restrained luxury | Photography, tight palette, sparse motion | Decoration competing with the product |
| Immersive motion | Choreography, spatial transitions, interactive scenes | Performance and access sacrificed to spectacle |

These are starting points, not industry rules. Use the actual brand, audience,
and brief to choose.

## Choose from the library

Read [techniques.md](techniques.md) for the candidate's purpose, implementation
shape, effort, fit, and failure cases. Pick the smallest intervention that
improves orientation, hierarchy, feedback, or storytelling.

For a new pattern, study a relevant public example if browsing is available.
Separate what you observed from what you inferred about how it was built.
Borrow the principle; use original or appropriately licensed code and assets.

The library describes approaches, not pinned dependencies. Follow the project's
existing stack and verify current APIs and browser support before implementation.
Do not add an animation library solely because it appears in an example.

## Give motion a reason

Describe what each significant animation helps the visitor understand. If the
only answer is "it moves," keep the content still.

Prefer transform and opacity when they fit the effect. Measure heavier effects
on representative devices. Keep content readable without an entrance animation,
respect reduced-motion preferences, and preserve native scrolling unless the
brief justifies changing it.

Decorative movement must not move a target away from a click, hide keyboard
focus, or delay an ordinary task.

## Check the finished interaction

Inspect the actual page at narrow and wide widths, with keyboard navigation
and reduced motion. Verify the primary action, anchor behavior, text wrapping,
and fallback states. Measure loading and interaction costs for heavy effects.

If rendering or device checks are unavailable, name those limits. Correct
source does not establish that the interaction feels right.

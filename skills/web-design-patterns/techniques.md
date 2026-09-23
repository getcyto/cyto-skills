# Technique library

Use each entry as a decision aid. Effort is relative to an ordinary page using
the project's existing stack; it is not a time estimate.

## Type and grid

- **Purpose:** Establish hierarchy through type scale, alignment, spacing, and a limited palette.
- **Build:** Semantic HTML and responsive CSS grid; test real content and long headings.
- **Kind / effort:** Static; modest.
- **Fits:** Reading, professional services, product explanations, editorial portfolios.
- **Backfires:** A rigid grid or fixed type size clips content on small screens.

## Masked headline reveal

- **Purpose:** Introduce a short headline through controlled pacing.
- **Build:** Animate a line inside an overflow mask using transforms. Recalculate masks when text wraps; preserve an accessible text representation.
- **Kind / effort:** Motion; modest.
- **Fits:** Editorial heroes, short section introductions.
- **Backfires:** Body text becomes slow to read, resize clips lines, or failed animation leaves words hidden.

## Photographic hero

- **Purpose:** Let an image establish the product, place, or craft.
- **Build:** Responsive images with intentional crops, appropriate resolution, reserved dimensions, and sufficient contrast for overlaid text.
- **Kind / effort:** Static; modest.
- **Fits:** Hospitality, physical products, visual portfolios.
- **Backfires:** Oversized downloads, unreadable text, or an image that conceals the primary action.

## Restrained parallax

- **Purpose:** Add depth to a limited photographic composition.
- **Build:** Move separate image layers at different rates within bounded ranges. Provide a static reduced-motion version.
- **Kind / effort:** Motion; moderate.
- **Fits:** A visual story with room around its reading content.
- **Backfires:** Motion behind body text, excessive movement, or poor performance on touch devices.

## Sticky walkthrough

- **Purpose:** Keep a visual in view while adjacent steps explain it.
- **Build:** Start with CSS sticky positioning and normal document flow. Add synchronized state changes only when they improve the explanation.
- **Kind / effort:** Static or motion; moderate.
- **Fits:** Product mechanics, process explanations, before-and-after narratives.
- **Backfires:** Too much pinned content makes scrolling feel stuck; short screens conceal steps.

## Horizontal gallery

- **Purpose:** Compare or browse a compact visual series.
- **Build:** Prefer a native overflow track with visible controls and keyboard access. If using a pinned scroll timeline, offer an ordinary layout on small screens.
- **Kind / effort:** Static interaction or motion; moderate.
- **Fits:** Portfolios and visual product stories.
- **Backfires:** Trapping vertical scroll, concealing later content, or replacing straightforward product browsing.

## Layout transition

- **Purpose:** Help visitors follow an item as a layout changes.
- **Build:** Capture the old and new geometry and animate between them, using existing platform or project tools. Preserve focus and stable item identity.
- **Kind / effort:** Motion; moderate.
- **Fits:** Grid/list toggles, filtering, expanding a card into detail.
- **Backfires:** Large lists cause expensive layout work, elements jump, or focus disappears.

## Reading progress

- **Purpose:** Give orientation within a long document.
- **Build:** Derive progress from the relevant scroll container. A CSS scroll timeline or a small script can drive a nonessential indicator; check support and keep a static fallback.
- **Kind / effort:** Motion; modest.
- **Fits:** Long-form reading and documentation.
- **Backfires:** Measuring the wrong container, implying completion from scroll alone, or obscuring content.

## Button feedback

- **Purpose:** Make hover, focus, pressed, loading, and completed states legible.
- **Build:** Use stable target geometry and brief state transitions; keep accessible names and visible focus.
- **Kind / effort:** Static interaction or motion; modest.
- **Fits:** Any action the visitor needs to recognize.
- **Backfires:** Moving click targets, hover-only information, or endless loading with no failure state.

## Marquee

- **Purpose:** Provide an optional ambient strip of short visual items.
- **Build:** Keep essential content available in a static form, hide decorative duplicates from assistive technology, and provide a way to stop persistent movement.
- **Kind / effort:** Motion; modest.
- **Fits:** Decorative brand rhythm when it does not compete with reading.
- **Backfires:** Important information can only be read while moving, or constant motion distracts from the page.

## Entry sequence

- **Purpose:** Set the tone for an experience where the introduction is part of the work.
- **Build:** Keep it brief, skippable, and tolerant of failed asset loading. Avoid replaying a blocking sequence on routine visits.
- **Kind / effort:** Motion; moderate to substantial.
- **Fits:** A deliberately immersive creative presentation.
- **Backfires:** Delaying booking, checkout, search, or access to ordinary information.

## Interactive 3D

- **Purpose:** Explain spatial form or let a visitor inspect a product.
- **Build:** Use optimized original or licensed assets, bounded loading, conventional controls, and a useful image-based alternative.
- **Kind / effort:** Motion; substantial.
- **Fits:** Products whose shape or configuration benefits from spatial inspection.
- **Backfires:** A heavy scene does the work of a simple photograph, or navigation requires a capable GPU.

## Before adding another effect

Check whether a simpler technique already serves the same purpose. Study the
whole interaction, including loading, errors, touch, keyboard, and reduced
motion. A demo's visual appeal is not evidence that it fits this page.

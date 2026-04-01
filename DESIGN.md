# Design System Strategy: Precision & Depth

## 1. Overview & Creative North Star

The **Creative North Star** for this design system is **"The Architectural Press."** 

In the world of high-end printing and packaging, every millimeter matters. This design system moves away from "web-native" generic layouts and adopts an editorial, structural approach. We treat the digital interface like a premium piece of embossed stationary: tactile, layered, and meticulously organized. 

By leveraging intentional asymmetry, oversized typography, and a "Tonal Layering" philosophy, we create an experience that feels as curated as a custom-printed luxury box. We break the grid not through chaos, but through calculated white space (using the `20` and `24` spacing tokens) to let elements breathe, signaling a brand that values quality over quantity.

---

## 2. Colors

The palette is derived from the signature dark cyan/teal of the logo, expanded into a sophisticated range of surface tiers.

### The Palette
*   **Primary (`#004e5d`):** Our foundation. Used for high-impact brand moments and heavy tonal sections.
*   **Primary Container (`#08677a`):** Used for interactive elements that need to stand out against the deep primary backgrounds.
*   **Surface & Neutrals:** We use a "Cool Slate" range (`#f8f9fa` to `#d9dadb`) to provide a clean, clinical contrast to the rich teal, emphasizing precision.

### The "No-Line" Rule
To maintain a high-end corporate feel, **1px solid borders for sectioning are strictly prohibited.** Do not use lines to separate content. Boundaries must be defined solely through background color shifts. For example, a `surface-container-low` section sitting on a `surface` background creates a clear, sophisticated boundary without the visual "noise" of a stroke.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers. Use the `surface-container` tiers (Lowest to Highest) to create depth.
*   **Base:** `surface`
*   **Nested Content:** `surface-container-low`
*   **Floating Elements:** `surface-container-lowest` (pure white `#ffffff`) to create a "lifted" paper effect.

### The "Glass & Gradient" Rule
For hero sections and floating navigation, use **Glassmorphism**. Apply semi-transparent surface colors with a `backdrop-filter: blur(20px)`. To add "soul" to the interface, use subtle linear gradients transitioning from `primary` to `primary_container` (e.g., at a 135-degree angle) for large CTAs and background accents.

---

## 3. Typography

The typography strategy pairs the geometric precision of **Manrope** for headings with the high-legibility of **Inter** for functional text.

*   **Display & Headlines (Manrope):** Use `display-lg` (3.5rem) and `headline-lg` (2rem) to create an editorial feel. These should be set with tight letter-spacing (-0.02em) to feel "pressed" and authoritative.
*   **Body & Labels (Inter):** All functional information uses Inter. `body-lg` (1rem) is the standard for prose. 
*   **Hierarchy as Identity:** Use high-contrast scaling. A small `label-md` (0.75rem) in all-caps with increased letter-spacing (0.05em) placed next to a `display-md` title creates a "spec-sheet" aesthetic that mirrors the precision of the printing industry.

---

## 4. Elevation & Depth

We avoid traditional material shadows in favor of **Tonal Layering**.

*   **The Layering Principle:** Depth is achieved by stacking. Place a `surface-container-lowest` card on a `surface-container-low` background. This creates a "soft lift" that feels architectural rather than digital.
*   **Ambient Shadows:** If a floating effect is required (e.g., a primary action button or a modal), use an ultra-diffused shadow: `box-shadow: 0 20px 40px rgba(0, 78, 93, 0.08)`. The shadow uses a tint of the `on-surface` or `primary` color, never pure black.
*   **The "Ghost Border" Fallback:** If a container requires definition on a complex background, use the `outline-variant` token at **15% opacity**. 
*   **Interactivity:** On hover, instead of a heavy shadow, shift the background color one tier higher (e.g., from `surface-container-high` to `surface-container-highest`).

---

## 5. Components

### Buttons
*   **Primary:** Background `primary`, text `on-primary`. Shape: `md` (0.375rem). Use for the main call to action.
*   **Secondary:** Background `surface-container-high`, text `primary`. Use for supporting actions.
*   **Tertiary:** No background. Text `primary` with an underline that appears only on hover.

### Cards
*   **Rule:** Forbid divider lines.
*   **Layout:** Use `padding: 1.5rem` (`6` spacing). Use `surface-container-lowest` to make cards "pop" against `surface` or `surface-dim` backgrounds. 
*   **Asymmetry:** Experiment with placing typography flush to the left while keeping icons or decorative "print marks" to the extreme right.

### Input Fields
*   **Style:** Minimalist. Use `surface-container-low` as the background fill. Use a bottom-only "Ghost Border" (2px) using `primary` only when the field is focused.
*   **Labels:** Use `label-md` in `on-surface-variant`, always positioned above the field, never as placeholder text.

### Chips & Tags
*   **Style:** Pill-shaped (`full` roundedness). Use `secondary-container` backgrounds with `on-secondary-container` text for a subtle, professional look.

---

## 6. Do's and Don'ts

### Do
*   **Do** use large amounts of white space (`16`, `20`, `24` spacing tokens) to signal luxury.
*   **Do** align text to a strict vertical axis to mimic professional typesetting.
*   **Do** use `primary` (Teal) as a background for high-conversion sections, paired with `on-primary` (White) text for maximum impact.

### Don't
*   **Don't** use 100% black. Use `on-surface` (`#191c1d`) for all "black" text to maintain tonal softness.
*   **Don't** use standard "drop shadows" with high opacity. 
*   **Don't** use sharp corners (`none`). Always use at least the `DEFAULT` (0.25rem) or `md` (0.375rem) roundedness to soften the corporate edge.
*   **Don't** use dividers or lines to separate list items; use a `surface-variant` background shift on hover or `1rem` of vertical breathing room.
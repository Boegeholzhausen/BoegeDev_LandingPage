# Design System Specification: The Kinetic Ether

## 1. Overview & Creative North Star
**Creative North Star: "The Kinetic Ether"**

This design system is built to move away from the static, "boxy" nature of traditional web development. It treats the interface not as a flat page, but as a deep, dimensional environment. By utilizing a "Kinetic Ether" approach, we prioritize fluid depth, light refraction, and intentional asymmetry to reflect the sophisticated nature of high-end app development.

We break the "template" look by avoiding rigid grid containers. Instead, elements should feel like they are floating in a pressurized, dark void, held together by gravitational balance rather than visible lines. Overlapping elements and high-contrast typography scales create an editorial rhythm that feels premium and bespoke.

---

## 2. Colors & Surface Philosophy

The palette is rooted in the `background` (#0b1326)—a deep, cosmic charcoal—layered with indigo and violet tokens to simulate light passing through glass.

### The "No-Line" Rule
**Explicit Instruction:** Traditional 1px solid borders for sectioning are strictly prohibited. Boundaries between sections must be defined solely through background shifts. 
*   Transition from `surface` to `surface-container-low` to signal a new content block. 
*   Use `surface-bright` for highlighting specific interactive zones without adding structural weight.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers. Use the surface-container tiers to create "nested" depth:
*   **Base:** `surface` (#0b1326).
*   **Secondary Content:** `surface-container-low` (#131b2e).
*   **Interactive Cards:** `surface-container-high` (#222a3d) or `highest` (#2d3449).
*   *Note:* An inner container should always be at least one tier "higher" or "lower" than its parent to define its importance through tonal contrast alone.

### The "Glass & Gradient" Rule
To achieve a signature high-tech feel, use Glassmorphism for floating elements. 
*   **Formula:** Combine `surface_container` at 60% opacity with a `backdrop-blur` of 20px. 
*   **Signature Textures:** Apply linear gradients transitioning from `primary` (#bdc2ff) to `primary-container` (#7c87f3) at a 135-degree angle for hero CTAs. This creates a "glow" effect that feels like energized hardware.

---

## 3. Typography

The typography strategy balances the precision of **Inter** with the architectural strength of **Manrope**.

*   **Display & Headline (Manrope):** Used for "Brand Moments." Use `display-lg` (3.5rem) with tight letter-spacing (-0.02em) to create an authoritative, editorial look. Asymmetric placement of headlines (e.g., left-aligned with significant right-side negative space) is encouraged.
*   **Body & Labels (Inter):** Used for utility and readability. `body-lg` (1rem) provides a clean, neutral counter-balance to the expressive headers.
*   **Tonal Authority:** Use `on_surface_variant` (#c7c4d7) for secondary body text to reduce visual noise while maintaining high legibility against the dark background.

---

## 4. Elevation & Depth

We achieve hierarchy through **Tonal Layering** rather than traditional shadows.

*   **The Layering Principle:** To "lift" a card, do not reach for a shadow first. Place a `surface-container-highest` card on a `surface` background. The shift in hex value provides a sophisticated, natural lift.
*   **Ambient Shadows:** For high-priority floating elements (like Modals or Navigation), use an extra-diffused shadow: `box-shadow: 0 20px 40px rgba(6, 14, 32, 0.4)`. The shadow color is derived from `surface-container-lowest` to ensure it looks like a natural occlusion of light.
*   **The "Ghost Border" Fallback:** If a border is required for accessibility, use the `outline-variant` (#464554) at **15% opacity**. This creates a "whisper" of an edge that defines the shape without interrupting the visual flow.
*   **Glassmorphism Depth:** When using glass components, use a top-down inner highlight (1px, `outline` at 10% opacity) to simulate the "edge" of a glass pane catching the light.

---

## 5. Components

### Buttons
*   **Primary:** Gradient fill (`primary` to `primary-container`). Roundedness: `md` (0.375rem). No border. Text color: `on_primary`.
*   **Secondary:** Ghost style. `Ghost Border` (outline-variant @ 20%) with a `surface-container-high` background on hover.
*   **Tertiary:** Text-only using `primary` color with a subtle `sm` spacing underline.

### High-End Cards
*   **Structure:** No dividers. Use `Spacing 8` (2.75rem) to separate internal header and body.
*   **Background:** `surface-container-low` with a subtle 135-degree gradient from `surface-container-highest` (top-left) to `surface-container-lowest` (bottom-right).

### Input Fields
*   **Style:** Minimalist. Background: `surface-container-lowest`. 
*   **Focus State:** The border transitions from "Ghost Border" to a 1px solid `primary` glow. Helper text uses `label-sm` in `on_surface_variant`.

### Signature Component: The "Code Glass" Terminal
*   A specialized container for displaying tech stacks. Uses a `surface_variant` background at 40% opacity, a heavy backdrop blur, and `secondary_fixed_dim` for syntax-highlighted text.

---

## 6. Do’s and Don’ts

### Do:
*   **Use Asymmetry:** Place a hero image offset from the grid to create a sense of motion.
*   **Embrace Negative Space:** Use `Spacing 20` (7rem) between major sections to let the high-tech elements "breathe."
*   **Color as Light:** Use `secondary` (#ddb7ff) sparingly as a "rim light" for small icons or active states.

### Don't:
*   **No Dividers:** Never use a horizontal line to separate list items. Use a 1-step tonal shift in the background or `Spacing 4` (1.4rem) of vertical gap.
*   **No Pure Black:** Never use #000000. It kills the depth of the indigo/violet gradients. Always stick to the `surface` tokens.
*   **No Standard Corners:** Avoid the `full` (pill) radius for anything other than Chips. Stick to `md` and `lg` for a more architectural, professional feel.
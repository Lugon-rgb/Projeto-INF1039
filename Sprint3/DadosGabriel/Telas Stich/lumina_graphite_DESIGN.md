# Design System Document

## 1. Overview & Creative North Star: "The Obsidian Curator"

This design system is engineered to transform a standard productivity utility into a high-end, editorial lifestyle experience. Our Creative North Star is **"The Obsidian Curator."** We move away from the "oppressive" nature of typical dark-mode grids by treating the interface as a series of precious objects floating in a deep, infinite space. 

By leveraging intentional asymmetry, generous negative space, and tonal layering, we eliminate the feeling of being "boxed in." The design breaks the standard template look by utilizing a sophisticated typographic scale and overlapping elements that suggest depth and physical presence, turning a simple tracking app into a digital sanctuary.

---

## 2. Colors

The palette is rooted in deep charcoal and absolute blacks, punctuated by high-vibrancy accents that serve as functional beacons within the interface.

### Tonal Foundations
*   **Background:** `#0d0e10` (The void; used for the primary canvas)
*   **Surface (Base):** `#0d0e10`
*   **Surface Container (Lowest):** `#000000` (Used for inset elements)
*   **Surface Container (Low):** `#121316` (Used for the first level of card separation)
*   **Surface Container (High):** `#1e2022` (Used for active or elevated states)

### Vibrant Accents (Status & Brand)
*   **Primary:** `#85adff` (The "Signature Blue" for actions)
*   **Secondary:** `#7f98ff`
*   **Tertiary:** `#fbb4ff` (For high-intent lifestyle triggers)
*   **Success (Green):** Integrated via custom status mapping.
*   **Error:** `#ff716c`

### The "No-Line" Rule
To ensure a breathable, premium feel, **1px solid borders are strictly prohibited** for sectioning or card definition. Boundaries must be defined solely through background color shifts. For example, a card (`surface-container-high`) should sit on a background (`surface`) without a stroke. The contrast in luminance provides the boundary, while the lack of a line allows the eye to flow across the layout without interruption.

### Glass & Gradient Implementation
To add "soul" to the UI:
*   **CTAs:** Use a subtle linear gradient from `primary` to `primary_container`.
*   **Floating Elements:** Apply **Glassmorphism**. Use semi-transparent surface colors with a `backdrop-filter: blur(20px)`. This allows the vibrant chart colors or status indicators to "glow" through the navigation or header bars, softening the overall experience.

---

## 3. Typography

The system utilizes a dual-font approach to achieve an editorial, bespoke aesthetic.

*   **Display & Headlines (Manrope):** Chosen for its geometric precision and modern character. Headlines use wide tracking and varied weights to establish an authoritative hierarchy.
*   **Body & Labels (Inter):** The workhorse font. Chosen for its extreme legibility at small sizes in dark-mode environments.

### Hierarchy Highlights
*   **Display LG (3.5rem / Manrope):** For hero statistics or high-impact lifestyle metrics.
*   **Title MD (1.125rem / Inter):** For card titles and primary navigation.
*   **Label SM (0.6875rem / Inter):** For secondary metadata (dates, small categories) with increased letter spacing for readability.

---

## 4. Elevation & Depth

We reject traditional structural lines in favor of **Tonal Layering**.

### The Layering Principle
Depth is achieved by "stacking" surface-container tiers. 
*   **Level 0:** `surface` (Background)
*   **Level 1:** `surface-container-low` (General content containers)
*   **Level 2:** `surface-container-highest` (Modals, floating menus, or high-priority cards)

### Ambient Shadows
When a floating effect is required (e.g., a "Nova Nota" button), use extra-diffused shadows:
*   **Blur:** 24px - 40px
*   **Opacity:** 4%-8%
*   **Color:** Tinted with `primary` or `on-surface` to mimic natural light dispersion rather than a muddy grey drop shadow.

### The "Ghost Border" Fallback
If a container requires extreme definition for accessibility, use the **Ghost Border**:
*   **Token:** `outline-variant`
*   **Opacity:** 10% - 15% 
*   **Weight:** 1px. 
*   *Note: Never use 100% opaque borders.*

---

## 5. Components

### Buttons
*   **Primary:** Rounded `full` (pill shape). Gradient fill (`primary` to `primary_container`). White text (`on_primary_fixed`) for maximum contrast.
*   **Secondary:** Ghost style. No fill, Ghost Border (15% opacity), and `primary` text.
*   **Tertiary:** Text-only, uppercase labels with 0.05em letter spacing.

### Cards & Lists
Cards must use `xl` (1.5rem) or `lg` (1rem) corner radii to feel "soft" and approachable. 
*   **Rule:** Forbid divider lines between list items. Use vertical whitespace (16px - 24px) or a subtle shift from `surface-container-low` to `surface-container-lowest` to separate data points.

### Charts & Indicators
*   **Progress Bars:** Use a high-vibrancy accent (e.g., `#85adff`) against a `surface-container-high` track. Add a subtle outer glow (2px blur) to the "active" portion of the bar to make it feel illuminated.
*   **Selection Chips:** Use `full` roundedness. Active chips should use `primary_container` with `on_primary_container` text.

### High-End Detail: The Lifestyle Note Card
On the "Notas" screen, cards should feature a **left-edge accent color bar** (4px width). This allows for color-coding (Health, Finance, Work) without overwhelming the card with a solid background color, maintaining the "breathable" requirement.

---

## 6. Do's and Don'ts

### Do
*   **DO** use asymmetric margins (e.g., a wider left margin for headlines) to create an editorial feel.
*   **DO** increase whitespace by 20% compared to standard Material Design grids to reduce the "oppressive" feel of dark mode.
*   **DO** use `surface_bright` for hover states to create a "lifting" effect.

### Don't
*   **DON'T** use pure `#000000` for all backgrounds; it creates "black smear" on OLED screens and feels too heavy. Use `surface` (`#0d0e10`) for the main canvas.
*   **DON'T** use high-contrast white text for body copy. Use `on_surface_variant` (`#ababad`) for a softer, more premium reading experience.
*   **DON'T** use 1px dividers. They create visual noise and clutter. Use space to define groups.
# Design System Document: The Athletic Editorial

## 1. Overview & Creative North Star
**Creative North Star: "The Kinetic Gallery"**

This design system moves away from the static, boxy nature of traditional sports management apps. Instead, it adopts an "Athletic Editorial" aesthetic—combining the high-energy movement of basketball with the prestigious, structured layout of a luxury sports magazine. 

We break the "template" look through **intentional asymmetry** and **overlapping elements**. By allowing player imagery or action cards to subtly break out of their containers, we simulate the "dynamic" nature of the sport. We rely on large-scale typography and breathable, layered surfaces rather than rigid grids to guide the eye, ensuring the experience feels as fluid as a fast break.

---

## 2. Colors & Surface Philosophy
The palette balances the heat of the game with the cool reliability of professional coaching.

### Palette Highlights
- **Primary Highlights:** `primary` (#994100) and `primary_container` (#ff7a23) provide the "Vibrant Orange" soul.
- **Foundational Trust:** `secondary` (#3d57a7) and `on_secondary_container` (#274292) deliver the "Deep Navy" professional grounding.
- **The Neutral Base:** `surface` (#f3f7fb) acts as our clean, breathable stadium floor.

### The "No-Line" Rule
To maintain a high-end feel, **1px solid borders for sectioning are strictly prohibited.** Boundaries must be defined through:
1.  **Background Shifts:** Place a `surface_container_highest` section against a `surface` background to define a zone.
2.  **Tonal Transitions:** Use soft shifts from `surface_container_lowest` (pure white) to `surface_container` to separate content blocks.

### The "Glass & Gradient" Rule
Standard flat buttons are insufficient for a brand named "Dazzling Suns." 
- **Signature Textures:** Use a subtle linear gradient from `primary` to `primary_container` (top-left to bottom-right) for primary CTAs to simulate the glow of a sun.
- **Glassmorphism:** For floating navigation bars or player "quick-view" overlays, use `surface` at 70% opacity with a `backdrop-blur` of 12px. This keeps the UI integrated with the action behind it.

---

## 3. Typography
We utilize a triple-font system to create a sophisticated hierarchy that feels both athletic and modern.

- **Display & Headlines (Lexend):** A geometric sans-serif that feels "strong and athletic." Use `display-lg` for impactful stats and `headline-md` for screen titles. The wide apertures of Lexend provide a modern, high-end look.
- **Titles & Body (Manrope):** A functional, modern sans-serif. Manrope acts as the bridge—professional and highly legible. `title-lg` should be used for player names and `body-md` for team communications.
- **Technical Labels (Plus Jakarta Sans):** Used for metadata, durations, and tactical tags. It provides a clean, technical contrast to the more emotive heading styles.

---

## 4. Elevation & Depth
Depth in this system is achieved through **Tonal Layering** and physical stacking, mimicking the layers of a basketball court.

- **The Layering Principle:** 
    - Base Level: `surface`
    - Section Level: `surface_container_low`
    - Content Card: `surface_container_lowest` (white)
    This "stacking" creates a soft, natural lift that avoids the cluttered look of heavy shadows.
- **Ambient Shadows:** When a card requires a "floating" state (e.g., a scheduled practice card), use a diffused shadow: `box-shadow: 0 20px 40px rgba(30, 58, 138, 0.06)`. The tint is pulled from our Navy `secondary` to feel natural, never grey.
- **The "Ghost Border" Fallback:** If a container absolutely requires a boundary (e.g., an input field), use `outline_variant` at 15% opacity. Never use 100% opaque lines.

---

## 5. Components

### Buttons
- **Primary:** Gradient (`primary` to `primary_container`), `xl` roundedness (3rem). Bold `lexend` type. High-contrast white text (`on_primary`).
- **Secondary:** `surface_container_highest` background with `secondary` text. No border.
- **Tertiary:** Transparent background, `secondary` text, with an underline only on hover.

### Cards & Lists (The "No Divider" Rule)
- **Cards:** Use `lg` (2rem) rounded corners. Forbid the use of divider lines. Separate content using `body-sm` (Manrope) for labels and generous vertical padding (24px - 32px).
- **Communication Threads:** Message bubbles use `xl` rounding on three corners and `sm` on the "tail" corner to create a modern, chat-oriented feel.

### Chips (Tactical Tags)
- Use `tertiary_container` for high-priority training tags (e.g., "MANDATORY").
- Use `secondary_fixed_dim` for filter chips.
- Shape: Always `full` (9999px) pills.

### Inputs
- Background: `surface_container_low`.
- Shape: `md` (1.5rem) for a friendly yet structured look.
- State: On focus, the "Ghost Border" becomes 100% `primary` orange.

### Specialty: The "Sunlight" Accent
- Incorporate a subtle, 10% opacity "sunburst" pattern (geometric radial lines) in the top-right corner of header containers to reinforce the brand identity without cluttering the UI.

---

## 6. Do's and Don'ts

### Do
- **Do** use negative space as a separator. If you think you need a line, add 16px of extra padding instead.
- **Do** use `primary_fixed` for "Active" states (e.g., live training sessions) to draw immediate focus.
- **Do** lean into the `xl` (3rem) corner radius for main action cards to create the promised "friendly yet modern" feel.

### Don't
- **Don't** use pure black (#000000). Use `on_surface` (#2a2f32) for all text to maintain an editorial, premium softness.
- **Don't** use standard Material shadows. Always use the Ambient Shadow formula (Navy-tinted, low-opacity).
- **Don't** cram icons. Let the typography do the heavy lifting for the brand's "Professional" and "Reliable" pillars.
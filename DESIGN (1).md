# Design System Document: The Sovereign Sentinel

## 1. Overview & Creative North Star
**Creative North Star: "The Digital Vault"**

This design system moves away from the "standard" legal website—which often relies on static imagery and rigid grids—and instead adopts an editorial, futuristic aesthetic. We are not just building a landing page; we are crafting a digital fortress. 

The "Digital Vault" concept uses deep, ink-like blacks and navies to represent stability and protection, punctuated by "Electric Blue" to signify innovation and "Gold" to denote premium success. We break the template look by utilizing **intentional asymmetry**: large display typography will often overlap container boundaries, and 3D-tilted glass cards will "float" in a non-linear arrangement to create a sense of three-dimensional depth and motion.

---

## 2. Colors & Surface Architecture

### The "No-Line" Rule
To maintain a high-end feel, **1px solid borders are strictly prohibited** for sectioning. Contrast and containment must be achieved through background shifts.
*   **Section Transition:** Use `surface` (#0c1324) for primary sections and `surface_container_low` (#151b2d) for secondary sections to create a soft, seamless transition.

### Surface Hierarchy & Nesting
Treat the UI as a physical stack of luxury materials. 
*   **Base:** `surface` (#0c1324)
*   **Nested Elements:** Place a `surface_container_high` (#23293c) element inside a `surface_container` (#191f31) to create a natural, "raised" feel without harsh lines.

### The Glass & Gradient Rule
*   **Glassmorphism:** For floating UI elements (like a sticky navigation or a 3D-tilted feature card), use `surface_variant` (#2e3447) at **40% opacity** with a `backdrop-filter: blur(20px)`.
*   **Signature Textures:** For primary CTAs, do not use a flat hex. Apply a subtle linear gradient (45deg) from `primary` (#f2ca50) to `primary_container` (#d4af37) to mimic the luster of physical gold.

---

## 3. Typography: Authority in Motion
We use **Inter** for its precision and technological feel.

*   **Display (The Bold Statement):** Use `display-lg` (3.5rem) with a negative letter-spacing (-0.02em). This is for "Hero" statements that command the room. 
*   **Headline (The Narrative):** `headline-lg` (2rem) should be used for section titles. Ensure these have ample line-height (1.4) to feel editorial.
*   **Body (The Fine Print):** Use `body-lg` (1rem) for general copy. Color should be `on_surface` (#dce1fb) but at **85% opacity** to reduce harsh contrast and increase the "premium" vibe.
*   **Labels (The Metadata):** Use `label-md` (0.75rem) in **Uppercase** with +0.1em letter-spacing for category tags or small "Above-Title" eyebrow text.

---

## 4. Elevation & Depth

### The Layering Principle
Depth is achieved through **Tonal Layering**. 
1.  **Level 0 (The Floor):** `surface_container_lowest` (#070d1f) - Use for the footer or deep background elements.
2.  **Level 1 (The Canvas):** `surface` (#0c1324) - The primary page background.
3.  **Level 2 (The Component):** `surface_container` (#191f31) - Cards or content blocks.

### Ambient Shadows
Traditional black shadows are forbidden. If a floating effect is required:
*   **Shadow Color:** Use a tinted version of `on_secondary_container` (the Electric Blue tone) at **6% opacity**. 
*   **Values:** `0px 20px 40px`. This mimics the glow of a high-end screen rather than a physical shadow.

### The "Ghost Border" Fallback
If a border is required for accessibility on an input or a button, use `outline_variant` (#4d4635) at **20% opacity**. It should be felt, not seen.

---

## 5. Components

### Buttons: The "Jewel" Interaction
*   **Primary:** A gradient-filled container (`primary` to `primary_container`). Text: `on_primary` (#3c2f00) in Bold. Shape: `xl` (0.75rem) roundedness.
*   **Secondary (Electric Blue):** A "Ghost" style. No fill. Border: `secondary` (#b8c3ff) at 30% opacity. On hover, the border glows with a 10px blur.
*   **Tertiary:** Text-only in `primary`. Interaction is a simple underline transition.

### Cards & Case Studies
*   **The 3D Tilt:** Feature cards must implement a `perspective: 1000px` CSS effect. On hover, the card tilts toward the cursor.
*   **No Dividers:** Never use horizontal rules. Use **48px - 64px of vertical whitespace** to separate case study entries.

### Input Fields: The "Secure Entry"
*   **Style:** `surface_container_highest` (#2e3447) background with a 1px "Ghost Border" that turns `secondary` (Electric Blue) on focus.
*   **Animation:** The label should float upwards and shrink to `label-sm` when the field is active.

### Floating Navigation (Glass)
*   **Style:** Position fixed, centered at the top. Use the Glassmorphism rule (40% opacity + blur). 
*   **Accent:** A 2px bottom border of `primary` (#f2ca50) that only spans the width of the active link.

---

## 6. Do's and Don'ts

### Do
*   **Do use asymmetrical margins.** Allow a "Hero" image to bleed off the right edge of the screen while text remains on the left.
*   **Do use "Electric Blue" as a functional accent.** Use it for links, hover states, and "Live" status indicators to show innovation.
*   **Do embrace "The Breath."** If a section feels crowded, double the white space. Premium brands aren't afraid of empty space.

### Don't
*   **Don't use 100% white (#FFFFFF).** It is too harsh for this dark theme. Use `on_surface` (#dce1fb) for all primary text.
*   **Don't use sharp corners.** Never go below the `md` (0.375rem) roundedness scale. Sharp corners feel aggressive; rounded corners feel "protective" and modern.
*   **Don't use standard easing.** Avoid `ease-in-out`. Use `cubic-bezier(0.22, 1, 0.36, 1)` (the "Expo" out) for all transitions to give a "snappy yet smooth" high-end feel.
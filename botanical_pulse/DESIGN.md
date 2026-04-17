# Design System Document: Anamour Natural Landing Experience

## 1. Overview & Creative North Star: "The Botanical Curated"
The design system for this experience is built on the **"Botanical Curated"** North Star. We are moving away from the "template" look of health and beauty sites by treating the digital canvas as a high-end editorial spread. 

The aesthetic is a tension between the **raw, energetic power of nature** (represented by the magenta and lush greens) and **disciplined, sophisticated structure** (represented by the stone neutrals and precise typography). We break the grid through intentional asymmetry—letting botanical imagery "bleed" off the screen or overlap nested containers—creating a sense of organic growth within a premium framework.

---

## 2. Colors & Tonal Architecture
The palette is a celebration of the dragon fruit’s vibrancy, grounded by stone and cream neutrals.

### The "No-Line" Rule
**Explicit Instruction:** You are prohibited from using 1px solid borders for sectioning. Boundaries must be defined solely through background color shifts. To separate a testimonial section from a product feature, transition from `surface` (#fffcf7) to `surface-container-low` (#fcf9f4). 

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers. Use the `surface-container` tiers to create "nested" depth:
*   **Base:** `background` (#fffcf7)
*   **Sectioning:** `surface-container-low` (#fcf9f4)
*   **Feature Modules:** `surface-container` (#f6f3ee)
*   **Elevated Details:** `surface-container-highest` (#eae8e2)

### The "Glass & Gradient" Rule
For floating elements or hero CTAs, use **Glassmorphism**. Apply a semi-transparent `surface-container-lowest` (#ffffff at 70% opacity) with a `backdrop-filter: blur(20px)`.
*   **Signature Textures:** For primary buttons and high-impact hero backgrounds, use a subtle linear gradient: `primary` (#c11661) to `primary-container` (#ff709e) at a 135-degree angle. This adds "soul" and depth that flat hex codes lack.

---

## 3. Typography: Editorial Precision
We use **Plus Jakarta Sans** exclusively to maintain a modern, clean, yet approachable voice.

*   **Display (lg/md/sm):** Used for "Hero" moments and section headers. High-contrast sizing creates an authoritative editorial feel. `display-lg` (3.5rem) should be used sparingly for maximum impact.
*   **Headline (lg/md/sm):** Use for sub-sections. These should feel energetic and bold.
*   **Title (lg/md/sm):** Use for product names and module headings.
*   **Body (lg/md/sm):** Set in `on-surface-variant` (#656461) to reduce visual vibration and improve readability against the cream backgrounds.
*   **Labels:** Reserved for small metadata or "over-line" categories. Always set in uppercase with 0.05em letter spacing for a premium feel.

---

## 4. Elevation & Depth: Tonal Layering
Traditional shadows are often a crutch for poor layout. In this system, we prioritize **Tonal Layering**.

*   **The Layering Principle:** Achieve lift by stacking. Place a `surface-container-lowest` card on a `surface-container-low` section. The slight shift in "brightness" creates a natural, soft lift.
*   **Ambient Shadows:** When a Floating Action Button (FAB) or glass card requires a shadow, it must be extra-diffused. 
    *   *Spec:* `0px 20px 40px rgba(56, 56, 53, 0.06)`. Note the use of the `on-surface` color (#383835) as the shadow base rather than pure black.
*   **The "Ghost Border" Fallback:** If accessibility requires a border, use `outline-variant` (#bbb9b4) at **15% opacity**. Never use a 100% opaque border.

---

## 5. Components

### Buttons
*   **Primary:** Rounded `full` (9999px). Gradient of `primary` to `primary-container`. White text. High-energy, organic feel.
*   **Secondary:** `surface-container-highest` background with `on-surface` text. No border.
*   **Floating Action Button (FAB):** The signature "Energetic" element. Uses `primary` background. Positioned with generous padding from the screen edge. Use glassmorphism logic if positioned over imagery.

### Cards & Lists
*   **Forbidden:** Divider lines. 
*   **Approach:** Use vertical white space (32px or 48px) and background color shifts to separate items. Card corners should use the `xl` (1.5rem) radius to feel soft and botanical.

### Input Fields
*   **Style:** Minimalist. `surface-container-low` background. 
*   **Focus State:** A 2px "Ghost Border" of `primary` at 40% opacity. Avoid heavy focus rings; keep it sophisticated.

### Signature Component: The "Organic Overlay"
*   **Description:** High-quality botanical imagery (dragon fruit, lush leaves) should occasionally overlap the boundary between two surface containers. This breaks the "box" feel and emphasizes the "Natural" brand identity.

---

## 6. Do’s and Don’ts

### Do:
*   **Do** use asymmetrical layouts. A text block on the left balanced by a botanical image that is slightly offset to the right.
*   **Do** embrace "Breathing Room." If you think there is enough whitespace, add 20% more.
*   **Do** use the `secondary` green (#336f54) for success states and "Natural Benefit" callouts to reinforce the botanical theme.

### Don’t:
*   **Don’t** use pure black (#000000) for text. Always use `on-surface` (#383835) to keep the look sophisticated and soft.
*   **Don’t** use standard "drop shadows." They look "cheap" in a premium system. Stick to tonal layering or the Ambient Shadow spec.
*   **Don’t** use sharp corners. Nature doesn't have 90-degree angles; your UI shouldn't either. Stick to the `md` through `xl` roundedness scale.

---

## 7. Imagery & Iconography
*   **Imagery:** High-definition macro photography. Focus on textures (the skin of a dragon fruit, dew on a leaf).
*   **Iconography:** Use light-weight (2pt stroke) icons. Icons should be `on-surface-variant` unless they are active, in which case they take the `primary` magenta.
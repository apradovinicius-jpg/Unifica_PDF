# Design System Strategy: The Obsidian Vault

## 1. Overview & Creative North Star
The Creative North Star for this design system is **"The Digital Vault."**

This is not a typical utility tool; it is a high-security, premium environment designed to house and manipulate sensitive documentation. We are moving away from the "flat web" aesthetic toward an experience that feels tactile, architectural, and authoritative.

The system breaks the "template" look by utilizing **intentional asymmetry** and **overlapping glass layers**. By allowing elements to bleed over container edges and using high-contrast typography scales, we create a sense of depth and curation. The interface should feel like a physical glass-and-metal console in a high-end secure facility—clean, bold, and visually striking.

---

## 2. Colors & Surface Philosophy
The palette is rooted in deep, atmospheric tones contrasted with neon-frequency accents.

*   **Primary (#CC97FF):** Used for "high-energy" actions and core branding.
*   **Secondary (#69F6B8):** Reserved for "secure" states, confirmation actions, and secondary progress indicators.
*   **Background (#060E20):** Our "Obsidian" base. All depth starts here.

### The "No-Line" Rule
To maintain a high-end editorial feel, **1px solid borders for sectioning are strictly prohibited.** Separation of concerns must be achieved through:
1.  **Background Color Shifts:** Moving between `surface-container-lowest` and `surface-container-high`.
2.  **Negative Space:** Using the 8-unit spacing scale to define boundaries.
3.  **Tonal Transitions:** Subtle shifts in dark values rather than hard lines.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers. Use the `surface-container` tiers to define "elevation" without shadows:
*   **Base:** `surface` (#0b1325).
*   **Major Sections:** `surface-container-low` (#131b2e).
*   **Interactive Cards/Panels:** `surface-container-high` (#222a3d).
*   **Active/Pop-out Elements:** `surface-container-highest` (#2d3448).

### The "Glass & Gradient" Rule
Floating panels, modals, and structured configuration panels must utilize **Glassmorphism**. Apply a `backdrop-blur` (12px–20px) to semi-transparent surface colors (e.g., `surface-variant` at 60% opacity). Main Call-to-Actions (CTAs) should use a linear gradient from `primary` (#dfbbff) to `primary-container` (#cc97ff) at a 135-degree angle to provide a "soulful" glow that flat hex codes cannot replicate.

---

## 3. Typography
The typographic identity relies on the tension between the geometric authority of **Lexend** and the technical legibility of **Manrope**.

*   **Display & Headlines (Lexend):** These are the "anchors." Use `display-lg` (3.5rem) with tight letter-spacing for hero sections. Headlines should be bold and assertive, conveying the "Vault" security and professional power.
*   **Body & Labels (Manrope):** High-readability sans-serif for structured configuration panels. We use `body-md` (0.875rem) as the standard to keep the interface feeling precise and information-dense.
*   **Hierarchy:** Always pair a large `headline-lg` with a significantly smaller `label-md` in `on-surface-variant` to create an editorial, high-contrast look.

---

## 4. Elevation & Depth
Depth in this system is a product of light and layering, not structural boxes.

*   **The Layering Principle:** Stack containers to create "natural lift." Place a `surface-container-lowest` card inside a `surface-container-low` sidebar to create an inset, recessed look that feels like a physical slot in the vault.
*   **Ambient Shadows:** If an element must float (like a context menu), use a shadow with a blur of 40px and 4% opacity. The shadow color should be `#000000` but softened by the glass blur beneath it.
*   **The "Ghost Border" Fallback:** If accessibility requires a border, use the `outline-variant` token at **15% opacity**. Never use 100% opaque lines.
*   **Signature Textures:** Incorporate a subtle noise texture (3% opacity) over the `background` to eliminate banding in gradients and give the "Obsidian" a premium, matte finish.

---

## 5. Components

### Buttons & Chips
*   **Primary Button:** Gradient-filled (`primary` to `primary-container`), rounded-md (0.75rem), with a subtle outer glow using the `surface-tint`.
*   **Secondary/Ghost:** `outline-variant` ghost border (20% opacity) with `on-surface` text.
*   **Chips:** Use for PDF metadata (e.g., "Encrypted," "OCR Ready"). These should be `surface-container-highest` with a `secondary` (mint green) dot for status indicators.

### Structured Configuration Panels
*   **The Panel Logic:** Configuration areas should use `surface-container-low` as a base. Group related settings into `surface-container-high` pods.
*   **Inputs:** Lexend for labels, Manrope for input text. Use `surface-container-lowest` for the input well to create a "recessed" feel. Focus states use a 1px `primary` glow.

### Lists & PDF Tables
*   **Forbid Dividers:** Use vertical white space (`spacing-4`) and alternating surface tones.
*   **Leading Elements:** Use `primary-container` for file icons to make them pop against the obsidian background.
*   **Interaction:** On hover, a list item should transition to a `glassmorphism` state (slight transparency + blur) rather than just a color change.

### The "Vault" Progress Bar
A custom component for PDF processing. A thick track in `surface-container-highest` with a `secondary` (mint green) glow-bar that pulses, indicating "active security."

---

## 6. Do's and Don'ts

### Do:
*   **DO** use asymmetric layouts. If a configuration panel is on the right, let the background imagery or branding elements bleed in from the left.
*   **DO** lean into the "Digital Vault" feel by using `secondary` (mint green) for all success or "locked" states.
*   **DO** use high-contrast type scales (e.g., 32pt headline next to 12pt metadata).

### Don't:
*   **DON'T** use pure white (#FFFFFF). Always use `on-surface` (#dae2fc) or `on-surface-variant` (#cec3d2) to protect the dark-mode eye strain and maintain the "Obsidian" mood.
*   **DON'T** use sharp 90-degree corners. Stay within the `md` (0.75rem) to `xl` (1.5rem) range for a sophisticated, modern feel.
*   **DON'T** use standard 1px borders. If you feel the need to separate, use a spacing gap or a tonal shift.
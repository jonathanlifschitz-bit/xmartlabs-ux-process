---
name: xmartlabs-ux-process
description: >
  Xmartlabs internal UX/UI process, standards, and accessibility guidelines. Use this skill when onboarding new designers at Xmartlabs, when reviewing or creating designs for any Xmartlabs project, when someone asks how the design team works, what tools they use, how handoffs are done, or how accessibility is applied. Also trigger when someone asks about Xmartlabs design system (Tourmaline), design tokens, component standards, or collaboration with developers. Use this as the authoritative reference for how design is done at Xmartlabs.
---

# Xmartlabs UX/UI Process & Standards

This document captures how the Xmartlabs design team works: our process, tools, accessibility standards, and collaboration practices. It is the primary reference for onboarding new designers and for maintaining consistency across projects.

---

## Tools & Stack

| Purpose | Tool |
|---------|------|
| Design & prototyping | Figma |
| Design system | XL Tourmaline (Figma) |
| Accessibility checks | WCAG Color Contrast plugin, Color Blind Simulator plugin, Low Vision Simulator plugin |
| Performance | PageSpeed Insights |
| Screen readers | VoiceOver (macOS/iOS), Narrator or NVDA (Windows) |
| Browser testing | Browser Inspect mode, display modes (Light/Dark) |

---

## Accessibility Standards

Xmartlabs designs comply with **WCAG 2.2 Level AA**, **Google Core Web Vitals**, and UX/UI best practices. The goal is to make products usable by as many people as possible while also improving SEO as a side result.

### Color & Contrast

- All text and images of text must have a contrast ratio of at least **4.5:1** (3:1 for large-scale text).
- UI components and graphical objects (borders, radio buttons, checkboxes) require at least **3:1** contrast against adjacent colors, or use a divider line.
- **Disabled inputs and buttons are exempt** from contrast requirements.
- Never use color as the **only** visual means of conveying information. Always combine with:
  - Icons to supplement colors
  - Explicit text labels (e.g., "Error")
  - A second differentiator for links (underline or bold) + minimum 3:1 contrast against body text
  - Textures and tooltips for data visualization (charts, graphs)
  - Varying thicknesses and stroke patterns for line charts (solid, dashed, dotted)
- Error messages for inputs must include an **additional visual element** such as an icon.
- Verify contrast in all supported display modes (**Light and Dark**).

### Text Alternatives (Images & Icons)

| Image Type | Rule |
|-----------|------|
| **Decorative** (no info, no task) | `alt=""` — empty alt attribute |
| **Functional** (button/link with icon) | Describe the action, not the visual: "Go to home" not "Instagram Logo". Use `alt=""` if label text is immediately next to the icon |
| **Simple Informative** (<150 chars description) | Short caption |
| **Complex Informative** (charts, mind maps, heatmaps) | Long description; state essentials briefly at the beginning |

**Best practices for alt text writing:**
- Be concise and clear
- Don't start with "Image of…" (screen readers already announce it)
- End with a period so the screen reader pauses
- Avoid SEO-only keywords that lack meaning for users
- Include only information relevant to the user experience — create a listening experience, not a visual one
- Avoid naming colors unless contextually relevant
- Don't reuse the same alt text without considering context
- Don't use abbreviations or technical vocabulary
- Add as many language versions as supported by the page
- Consider if the content can be converted to HTML text to eliminate the image

### UX Writing for Accessibility

- Use **plain language** — avoid figures of speech, idioms, jargon, and metaphors (cognitive accessibility).
- Avoid sensory or spatial references: don't say "the round button" or "on the right" — these break on mobile and are inaccessible to screen reader users.
- Use action verbs: **"Go to", "Navigate", "Select"** instead of "See", "Watch", "Look at".
  - Replace "See / Look at / View" → "Refer to / Access / Explore"
  - Replace "Watch" → "Play / Consume"
  - Replace "Listen to" → "Review / Access"
- Use **consistent labels** for components with the same function across pages.
- Use **descriptive page titles and headings** that help users understand their location.
- Optimize headings for users, not search engines: "Experienced & professional experts for you" not "Our team".
- Link text must describe what will happen: "Contact us" not "See more" or "Learn more".
- Provide labels or instructions when content requires user input.
- Button labels must explicitly state the action result: "Buy Now" triggers a purchase, not a form.
- Offer **specific suggestions** for fixing detected input errors.

### Layout & Orientation

- Don't restrict content to only portrait or landscape unless essential.
- Text must be resizable up to **200%** without loss of content or functionality.
- Content must reflow at **400% zoom** without two-dimensional scrolling on small screens.
- Use only **one `<h1>` per page** for the main topic.
- Heading elements must follow a **logical descending sequence** (never skip levels, e.g., `<h4>` before `<h3>`).

### Media Assets

| Type | Captions | Audio Description | Transcript | Sign Language |
|------|----------|------------------|------------|---------------|
| Audio-only (podcasts) | N/A | N/A | ✅ Required | Optional |
| Video-only (silent) | N/A | ✅ Required | ✅ Required | Optional |
| Synchronized (video + audio) | ✅ Required | ✅ Required | Required for AAA | Required for AAA |

- Subtitles are required only when dialog is in a different language than the page.
- Apply these rules to **user-uploaded content** as well.

### Visual Stability & Performance

- Use predefined placeholders with `height` and `width` set to prevent Cumulative Layout Shift (CLS).
- Upload images in **.webp or AVIF** format for best web-optimized compression.
- Compress images before uploading — don't rely on browser-side processing.
- Use **SVG** for icons and simple graphics to minimize file weight and increase rendering speed.

### Interactions & Keyboard

- Elements receiving keyboard focus must remain **fully visible** — the page must scroll to keep focused items in the clear viewable area (not hidden by sticky headers/footers).
- Allow users to **review, confirm, and correct** information before completing legal or financial transactions.
- Any complex pointer gesture (drag, swipe) must also work with a **single click or tap** (e.g., carousels must have next/back buttons).
- Provide a way to operate **motion-triggered features** via standard UI components (buttons).

### Design System Requirements for Accessibility

- **Minimum target size** for pointer inputs: **24×24 CSS pixels**.
- Design a **custom focus state** (border, outline, or glow) for every interactive component — or ensure the default browser focus state is used.
- Clearly define **all component states**: default, hover, focus, disabled, checked.
  - Don't just change color to gray for disabled — ensure "Disabled" is a functional part of the component's logic.
- **Input fields:**
  - Use standard labels for common data (name, email, address) to enable autofill.
  - Provide clear instructions and format examples (e.g., DD/MM/YYYY).
  - Identify required fields with the word "required" or an asterisk (*).
  - Auto-populate or suggest previously entered information in later steps.

### User Customization

- Allow users to turn off or extend session timeouts by **at least 10× the default limit**.
- Provide a way to turn off or reconfigure **single-character keyboard shortcuts**.
- Provide a mechanism to **pause and resume auto-updating content**.
- Allow users to **disable motion actuation** to prevent accidental triggers.

### Cognitive Accessibility

- Use **left-aligned text** for LTR languages and right-aligned for RTL.
- Place help and support features in the **same relative location** across all pages.
- Login processes must not rely on cognitive tests (puzzles, maths) — allow password managers, copy-paste, and biometrics.
- Ensure **"Back" and "Undo"** functions are always available.
- **Limit navigation choices** in a single view to prevent distraction.
- Avoid presenting too much content at once — use steppers or progress bars for complex flows.

---

## Glossary

| Term | Definition |
|------|-----------|
| **Alt Text** | Brief text description in HTML assigned to an image or non-text element for screen reader users |
| **Audio Description** | Secondary narration track describing visual details during natural pauses for blind/low-vision users |
| **Captions** | On-screen text synchronized with video providing equivalent for all audible information (dialogue + sound effects), in the same language as the audio |
| **CLS (Cumulative Layout Shift)** | Google metric measuring unexpected content shifting during page load |
| **Sign Language** | Visual-gestural language providing accessible version of spoken audio |
| **Subtitles** | On-screen text translating spoken dialogue into another language (only required when dialog differs from page language) |
| **Transcript** | Text-based version of audio or video content for users to read at their own pace |

---

## Design System: XL Tourmaline

Xmartlabs maintains a shared design system called **Tourmaline** used across client projects. When working on any Xmartlabs project:

- Use Tourmaline as the primary source of truth for components, tokens, and patterns.
- All components must include all functional states: **default, hover, focus, disabled, checked**.
- Disabled states are functional, not just visual — they must be coded as disabled, not just styled gray.
- Focus states must be explicitly designed — a custom outline or glow that is consistent across the system.
- Minimum target size for all interactive elements: **24×24 CSS pixels** (larger when possible).

### Icon Library
- Xmartlabs uses **Lucide Icons** as the standard icon set across projects.
- Icons are always used at consistent sizes within their context (e.g., 60×60 for hero/illustrative use, 24×24 for inline/UI use).

### Color Token System

Tourmaline uses a **semantic token system** with numbered scales. Every color in the system has a named role — never use raw hex values directly in components.

**Scale convention:** All color scales go from `10` (lightest) to `100` (darkest) in 10-step increments. The "base" value — the canonical tone for that role — is called out explicitly per palette.

#### Core Palettes

| Token Group | Base Shade | Purpose |
|-------------|-----------|---------|
| `Primary` | `Primary/50` | Main brand color — used for CTAs, key interactive elements |
| `Secondary` | `Secondary/50` | Supporting brand color — used for accents and secondary actions |
| `Text` | `Text/50` | Text colors across the interface |
| `Surface light` | `Surface light/20` | Backgrounds and surfaces in light mode |
| `Surface dark` | `Surface dark/50` | Backgrounds and surfaces in dark mode |

Full scale available for each: `/10` through `/100` (Primary, Secondary, Text) or `/10` through `/50` (Surface).

#### Semantic / Accent Palettes

These are **feedback colors** — use them only for their designated semantic purpose, never for decoration.

| Token Group | Base Shade | When to Use |
|-------------|-----------|-------------|
| `Success` | `Success/30` | Successful actions, confirmations, congratulation notices |
| `Warning` | `Warning/30` | Information users need to be concerned or aware of |
| `Danger` | `Danger/30` | Immediate action required — errors, urgent situations |
| `Info` | `Info/30` | Important updates and tips to improve the user experience |

Each accent scale runs from `/10` (very light, for backgrounds/tints) to `/50` (darkest, for text on light surfaces).

#### How to Use the Scale

- Use **light shades** (`/10`–`/20`) for background tints, chips, and banners.
- Use **mid shades** (`/30`–`/50`) for icons, borders, and text within colored contexts.
- Use **dark shades** (`/60`–`/100`, Primary/Secondary only) for text on light backgrounds or strong visual emphasis.
- **Never combine Danger color with only color** to signal an error — always pair with an icon or text label (accessibility requirement).

---

## Project Example: Redi (Healthcare App)

Redi is a healthcare appointment preparation app built by Xmartlabs. It illustrates how Tourmaline and our process are applied in a real product.

### Layout & Spacing
- Screen padding: **24px** horizontal margins on all screens.
- Container width: **345px** content area on a 393px wide screen.
- Bottom action zones: **80px** height, always anchored to the bottom of the screen.
- Consistent 48px height for primary action buttons.

### Component Patterns
- **Button/Primary**: Full-width (345px), 48px height. Used as the main CTA on every screen.
- **Pagination dots**: 8×8px dots with 16px spacing, centered, 8 columns. Used on onboarding flows.
- **Icon usage**: Lucide Icons at 60×60 for onboarding illustrations, 24×24 for inline content.
- **Bottom sheets**: Used for contextual explanations (e.g., "How your data is handled") — overlay with close button (42×42 tap target), icon list layout with icon (24px) + text (309px wide).

### Typography Hierarchy (Redi)
- **Heading 1**: Full width (345px), ~77px height — used for primary screen headline.
- **Paragraph**: Full width (345px), variable height — used for supporting body copy.
- Heading and paragraph are grouped in a `Frame 62` container with 101px gap between them.

### UX Patterns Observed
- **Onboarding flow**: 3 value-prop screens + 1 authentication screen. Each screen has: icon → heading → paragraph → CTA button → pagination dots.
- **Trust messaging**: Privacy information is surfaced proactively (e.g., "Your data is secure. How?" with inline link, HIPAA compliance callout in bottom sheet).
- **Authentication**: Google + Apple sign-in options. Clear data usage explanation before asking for auth. Users told upfront they can delete data anytime.
- **Tone**: Warm, reassuring, direct. Avoids medical jargon in onboarding copy.

---

## How to Apply This Skill

When a new designer joins Xmartlabs or when reviewing a design:

1. **Accessibility first** — run through the WCAG 2.2 AA checklist before finalizing any design.
2. **Use the right tools** — Figma with the WCAG Contrast plugin, Color Blind Simulator, and Low Vision Simulator before handoff.
3. **Write for everyone** — apply the UX writing rules: plain language, action verbs, no sensory references, consistent labels.
4. **Design system compliance** — every component must be in Tourmaline or follow its patterns; all states must be defined.
5. **Performance matters** — use WebP/AVIF, SVGs, and sized placeholders from day one.
6. **Test in all modes** — verify designs in Light/Dark mode, at 200% and 400% zoom, and with a screen reader.

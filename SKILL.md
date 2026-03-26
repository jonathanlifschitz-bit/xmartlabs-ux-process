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

## The Xmartlabs Service

### What We Do

Xmartlabs is a **Digital Product Studio** working with startup founders and product managers who need to build or evolve a digital product. There are two main engagement types:

**1. MVP / V1 Development**
For startup founders (often non-technical) who want to bring their product vision to market.
- The detailed vision may not be fully defined or market-validated yet.
- Strong time and budget constraints — they want to ship fast, well, and within budget.

**2. Product Evolution**
For products already in the market, usually brought by PMs looking for a stronger team to keep growing the product.
- Need support on product evolution decisions (what features to include and how long they take).
- Multiple versions run in parallel: v1 in production, v2 in dev, v3 in design, v4 in exploration.

---

## Design Process

### Overview

Every project goes through the following stages. Some stages are more compressed for MVPs; all stages exist in full for product evolution engagements.

| Stage | Who leads |
|-------|-----------|
| Discovery & Pre-Sales | Sales + Pre-Sales team |
| Research & Analysis | Product Designer + PM + Engineering |
| Branding | Designer |
| UX Design & MVP Analysis | Product Designer |
| UI Design & Design System | Designer |
| Handoff | Designer |
| Support (during development) | Designer |
| Product Evolution | Full team |

---

### Stage 1: Discovery & Pre-Sales

The commercial and pre-sales team has the first contact with the client. Goal: understand the challenge and validate feasibility.

**What happens:**
- Initial research and analysis: competitive study, risk analysis, tech stack alternatives.
- "Ballpark" estimate based on project type.

**Output — Service Proposal containing:**
- Problem, target audience, and opportunity
- Product vision and value proposition
- Possible initial feature set
- Suggested tech stack
- Tentative roadmap for Research, Design, Development, and Release

---

### Stage 2: Research & Analysis (Discovery)

**Objectives:**
1. Define and validate the problem.
2. Design the best version of the product achievable within the available time.

> Example: The client wants to build an Uber for bikes. We define that in 3–4 months we can have a V1 with the core functionalities. During the process, the objective and timeline are fixed; what's flexible is the concrete scope — number of features, quality of each implementation, etc.

**Mindset — Lean Approach:**
Product, design, and development teams work together throughout this stage. Everyone is responsible for understanding the problem, doing research, grounding the product in wireframes, reviewing how long alternatives will take, and converging with the client on a clearly scoped V1.

The stage is structured in 3 phases:

---

#### Phase 1 — Research (1–2 weeks)

Goal: The team immerses itself in the problem and collectively grounds the understanding.

**Step 1 — Discovery (Understanding Meeting)**
Kick off with a client meeting to revisit and deepen the product vision. In parallel, the team does preliminary research on the product, competition, and industry.

**Step 2 — Preliminary Research**

Methods:
- **Desk Research (primary and secondary):** online search, podcasts, conferences, reading about competitors, scholarly research.
- **Self-ethnographic research:** explore the experience yourself in a real situation context — try existing products, summarize public reviews from stores and forums.
- **Participant approaches:** user interviews, participant observation.

**Step 3 — Research Visualization**

After individual research, the team meets to present insights and work on mapping together.

Outputs:
- **Problem Statement** — *"The current state of [domain] has focused primarily on [segments/pain points]. What existing products fail to address is [gap]. Our product will address this by [vision]. Our initial focus will be [segment]."*
- **Business Outcomes** — high-level outcomes affecting the business (use AARRR framework: Acquisition, Activation, Retention, Referral, Revenue).
- **Proto-Personas (3–4)** — sketch/photo, name, role, factors influencing behavior, needs/obstacles/desires. Used as recruiting targets for validation.
- **User Outcomes** — what is the user trying to accomplish? How do they want to feel? How does the product get them closer to a life goal?
- **Feature Hypothesis Table (Lean UX):**

| Business Outcome | Persona | User Outcome | Feature |
|-----------------|---------|-------------|---------|
| We will achieve... | if [persona]... | can achieve... | with this feature |

- **Journey Maps** (when relevant)
- **Stakeholder / Ecosystem Maps** (when relevant)

**Step 4 — Validation**

The research visualizations are hypothesis-based until validated with real users. User discovery interviews confirm that the team's understanding of the problem is accurate. After interviews, iterate on all diagrams.

---

#### Phase 2 — Ideation & Prototyping (1–2 weeks)

Goal: Design the solution for the MVP and validate it.

Steps:
1. **Ideation** — generate a list of ideas and features (with the dev team).
2. **Define** — feature prioritization → MVP scope + flow map (with the dev team).
3. **Design** — wireframes (with multiple alternatives) + tech validation.
4. **Prototype** — basic lo-fi prototype.
5. **Validation** — user interviews with the lo-fi prototype (with the dev team).

**Important:** Think about and recommend what the product should *not* do and what can be done manually instead (classic example: PedidosYa's MVP had a web interface, but someone manually called the restaurants).

**Scope definition outputs:**
- **Product Backlog** — list of flows/features included in V1 (and what's deferred). For each feature: brief intro, research links, discussion. During this stage the docs serve as a guide; detailed specs are filled in later during development.
- **Flow Map** — diagram representing all logic and functionalities that will appear in the MVP. Reviewed by development for technical validation.

---

#### Phase 3 — UX Design (1 week)

Goal: Close out the detailed UX flows.

Steps:
1. **Design** — iterate on the flow map with wireframes.
2. **Prototype** — update the prototype.
3. **Test** — validate the updated prototype.

---

**Typical Discovery Timeline (4 weeks):**

| Week | Designer | Meetings |
|------|----------|---------|
| 1 | Preliminary research | Understanding meeting |
| 2 | Research + Research Visualization session | Schedule user interviews |
| 3 | User interviews | Review research + first solution vision |
| 4 | Flow map + wireframes | Review MVP flow map |

Full timeline runs ~15 working days with user interview rounds at weeks 3 and 4.

---

**Discovery Deliverables Summary:**

| Category | Artifact |
|----------|---------|
| **Product** | Vision documentation (problem, research), Product Backlog, Product Specs |
| **Design** | Product Flow Map, Lo-fi prototype |
| **Development** | Tech approach — validated solutions to main technical challenges |

---

### Stage 3: UX Design & MVP Validation

**Wireframing and prototyping:**
- 2–3 iterations of wireframes, grounding the core flows and defining navigation logic.

**User testing:**
- When possible, the low-fidelity prototype is validated with potential users.
- In some cases the client takes the Product Manager role for this validation.

**Output:**
- Closed MVP scope with revised roadmap and detailed development plan.

---

### Stage 4: Branding

**What branding is at Xmartlabs:**
The branding process at Xmartlabs is not a full brand identity engagement (as expected from a branding agency). It's a condensed, efficient process — typically an add-on to the MVP design service — focused on getting the product to market. It helps clients establish the foundations of their brand and define a first visual direction.

**Timeline:** ~1 week.

---

**Step 1 — Product Understanding**
Review and deepen the basic elements of the product and company already discussed in earlier stages.

**Step 2 — Brand Definition (client workshop)**

Run a meeting with the client using these exercises:
- **Personality Sliders** — position the brand on key spectrums.
- **Personality Quadrants** (Tone, Language, Purpose) — define the brand's character.
- **Style References Review** — review references together.

**Step 3 — Partido Conceptual (Brand Concept)**

Define the product in a single sentence that:
- Can be referenced at any stage of the process.
- Prevents drifting from the brand objective.
- Is specific enough to generate distinct visual directions from it.

This concept is the strategic anchor for all visual exploration.

**Step 4 — Define 3 Visual Lines to Explore**

Each line makes a different visual bet, emphasizing a different aspect of the brand concept.

*Example from Lowrider project:*
- **Friendly comrade** — Personal assistant fighting for justice for you (with data). Visual: Fun + Simple, Modern, Retro-Serif, Friendly, Playful.
- **Smart assistant** — Easiest way to get the best deal. Just drive and we take care of you. Visual: Modern + Clean, Some fun/delight, Humble, Softer.
- **Funky** — Lifestyle insurance for your car. Visual: Energetic/Dynamic, Sleek and Bold, Personality.

**Step 5 — Styles Exploration**

For each of the 3 visual lines, collect references across these categories:
- Logo style
- Typography
- Color Palette
- Voice & Tone
- Shapes
- Illustrations / Images
- Icons
- Texture
- Composition
- Photos reflecting the look & feel
- UI Design references
- Hero Shots

Do this collaboratively — each person understands the same concept differently, and the discussion makes the output stronger.

**Step 6 — Styles Exploration Presentation (client)**

Present the 3 moodboards to the client:
- Explain that the styles are intentionally extreme to enable exploration — the brand can land somewhere in between.
- Give the client a minute of silence to look at all moodboards before presenting.
- Walk through each proposal element by element, explaining decisions.
- Explain the specific message each style reinforces and how it links to visual choices.

*Output:* clear understanding of what the client likes and doesn't like from each direction.

**Step 7 — Stylescapes**

Build one Stylescape per direction (or a refined combined one) based on the moodboard feedback.

- Format: **4000×750 pt @ 2x**.
- The Stylescape is a narrative composition — it tells the story of the brand's feel, not just shows colors and fonts.
- Reference: [TheFutur Stylescape course](https://www.thefutur.com) for structure and narrative approach.

**Step 8 — Stylescape Iteration & Wrap-up**

Iterate on the chosen Stylescape based on client feedback until validated.

The final Stylescape becomes the **north star** for all subsequent product design:
- Return to it during UI design to validate: *"Does this screen transmit what we defined here?"*
- If the UI drifts from the Stylescape's feel, course-correct.

---

**Branding Roadmap (1 week):**

| Day | Work | Meetings |
|-----|------|---------|
| 1 | Internal research + preparation | Brand Definition meeting with client |
| 2 | Brand concept | Internal brand concept meeting |
| 3–4 | Stylescapes design | Internal Stylescape review |
| 4–5 | Stylescape polish | Stylescape presentation to client |
| 5 | Stylescape iteration | Stylescape wrap-up meeting |

---

### Stage 5: UI Design & Design System

**Goal:** Generate all screens and resolve the details needed to implement the product. The better the documentation, the easier the implementation, quality, and future maintenance.

> A product with custom components built without documentation ends up as a lower-quality product — unless the development team makes all those decisions during development (and makes them well). Good UI documentation prevents that.

The stage is divided into 4 sub-stages:

---

#### 5a — UI Style Exploration

Before defining the full design system and component library, validate the visual direction quickly by designing **3–5 central screens** at high fidelity.

This is the most important sub-stage: it's where the look and feel of the app is decided. The rest of the process refines and details — but the soul of the design is defined here.

**Steps:**
1. **Research** — revisit competitors and the state of the art. If pursuing a specific trend, explore UI Kits (e.g., Uplabs).
2. **UI Design** — design the 3–5 key screens at high fidelity.
3. **Internal review.**
4. **Iterate** — refine based on internal feedback.
5. **Client validation** — present the UI style to the client.
6. **Iterate** — refine based on client feedback.

**Additional considerations for this stage:**
- Think about **motion, animations, and haptic feedback** — not just static pixels.
- Align on: logo status, typography licenses, illustrations, photography, and content generation.

---

#### 5b — Design System Setup

Once the visual style is validated, work with the dev team to ground it into a structured design system. This includes defining foundations (colors using Tourmaline token structure, typography, grid, spacing, shadows), auditing which components Tourmaline already covers, and identifying what needs to be created. Always align with the dev team on the technical stack before building components — the framework's available components shape what needs to be designed.

---

#### 5c — Interface Design (Full Flow)

Design all remaining screens and flows.

**Steps:**
1. **Draw screens and assemble flows:**
   - Design all UI screens (consider haptic feedback for interactive components).
   - Technical validation with devs.
   - Validate designs internally and with the client.
2. **Define analytics:**
   - Define events and funnels — map the series of events that lead to key goals (e.g., ad-to-purchase journey, user engagement to sale).
   - Funnels must be defined during design, not retrofitted after launch.

**Content areas that require special attention:**
- Navigation and dropdowns
- Form fields and validation messages
- Tooltips and error messages
- Charts and image captions
- Loading screens and confirmation pages
- Product support documentation

Content is a UI element — body copy, list items, table content, labels — all require the same design attention as visual components.

---

#### 5d — Handoff

Wrap up and package everything the development team needs to implement the product.

**Checklist:**

- [ ] Generate a **copy & translations document** (for multi-language apps/webs).
- [ ] Deliver **general assets**: app icons for dev and test, app typography files.
- [ ] For each **Feature or Module**:
  - Feature product documentation (about + considerations) in Notion.
  - Flowmap in Figma — with links to each flow.
  - Assets (if needed) — link to Google Drive.
- [ ] **Style Guide (Design System Foundations):**
  - Component documentation (UX behavior) in Notion.
  - For each custom component: define all behavior and UX states.
- [ ] Product documentation (separate from product specs & roadmap).
- [ ] Other deliverables: store assets, app store screenshots, etc.

---

### Stage 6: Handoff

This phase involves sharing with the dev and QA teams the final user journeys and specifications: colors, spacing, type styles, measurements, and all assets needed to implement the product.

**What gets delivered:**

**Design System**
The design system is foundational to consistency and efficiency. It establishes guidelines for colors, spacing, and typography — ensuring cohesive visual identity across the product. Development actively uses it; the designer's role during handoff is to ensure it's complete, organized, and prevents both deviations from guidelines and unnecessary component duplication.

**Assets**
- **Icons and images** — exported in the format agreed with dev (SVG, JPG, or PNG depending on platform and technology). Always consult with dev before exporting.
- **App Store screenshots** — tailored for App Store and Google Play, showcasing the app in its marketplace environment.
- **App icons** — Android icon, Android notification icon, iOS icon — all sizes and formats required for uniform branding across devices.

**Edge Cases & Empty States**
Design must cover not only primary user interactions but also:
- Scenarios where users encounter no content (empty states).
- Unexpected situations or errors within the interface.
These must be designed and documented before handoff, not left for devs to improvise.

**Animations & Micro-interactions**
Define animations by finding references and creating prototypes directly in Figma. Alternative tools: After Effects, InVision, Marvel. The goal is clear communication with developers so animations are implemented cohesively and aligned with the design vision.

---

### Stage 7: Support (During Development)

**Design Review**
During this phase, review development work against the Figma file to identify discrepancies and report them. Reporting method depends on the project (Jira, Bugsee, etc.).

- If there's a QA team: they do the first pass. The designer does a second, more detailed review after QA validation.
- If there's no QA team: the designer handles all design validation.

**Ongoing Design Work**
Despite thorough planning, some assets, sub-flows, and interactions won't be covered upfront — it's impossible to anticipate every scenario in static design. These emerge during development and require collaborative problem-solving between designer and dev. This includes:
- Missing documentation
- Updated product specifications
- New components and secondary flows
- Border cases and empty states not initially covered

**Collaboration with QA**

The QA ↔ Designer workflow:

1. **QA studies the Figma file** — asks questions, detects errors, finds uncovered edge cases. Back-and-forth with the designer until aligned. Dev team joins as needed for technical clarifications.
2. **QA compares deployed product to Figma** — identifies discrepancies, reports them as bugs in Jira.
3. **Designer does second-pass review** — covers details after QA's initial pass. Upon dev confirmation that changes are implemented, QA validates the Jira tasks.
4. **QA reviews new Figma designs** — since QA knows the app in detail, they review new designs to verify that new components maintain the same hierarchy and behavior patterns as the rest of the app. This ensures consistent UX across versions.
5. **QA validates prototypes before client delivery** — when the design team creates Figma prototypes for the client, QA ensures all paths work correctly before the link is sent.

---

### Stage 8: Product Evolution

After the first release, projects enter continuous development. The cadence:

- **Bi-weekly meeting** to:
  - Review product insights and metrics (how is it performing?).
  - Discuss potential changes or new features — these enter a research and analysis pipeline: scoped, ideated, roughly estimated, then prioritized.
  - Prioritize features and plan upcoming versions.

- **Parallel version tracks:**
  - v1 in production
  - v2 in development
  - v3 in UI design
  - v4 in analysis/exploration

---

## How to Apply This Skill

When a new designer joins Xmartlabs or when reviewing a design:

1. **Accessibility first** — run through the WCAG 2.2 AA checklist before finalizing any design.
2. **Use the right tools** — Figma with the WCAG Contrast plugin, Color Blind Simulator, and Low Vision Simulator before handoff.
3. **Write for everyone** — apply the UX writing rules: plain language, action verbs, no sensory references, consistent labels.
4. **Design system compliance** — every component must be in Tourmaline or follow its patterns; all states must be defined.
5. **Performance matters** — use WebP/AVIF, SVGs, and sized placeholders from day one.
6. **Test in all modes** — verify designs in Light/Dark mode, at 200% and 400% zoom, and with a screen reader.

---
name: xmartlabs-ux-process
description: >
  Xmartlabs internal UX/UI process and standards. Use this skill when onboarding new designers at Xmartlabs, when reviewing or creating designs for any Xmartlabs project, when someone asks how the design team works, what tools they use, how handoffs are done, or how the design process is structured. Also trigger when someone asks about Xmartlabs design system (Tourmaline), design tokens, component standards, or collaboration with developers. Use this as the authoritative reference for how design is done at Xmartlabs. For detailed accessibility checklists and WCAG compliance, use the accessibility-xl skill instead.
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

Xmartlabs designs comply with **WCAG 2.2 Level AA**, **Google Core Web Vitals**, and UX/UI best practices. The complete accessibility checklist — covering color contrast, alt text, UX writing, keyboard interactions, media assets, cognitive accessibility, and design system requirements — is maintained in the **`accessibility-xl` skill**.

When reviewing any design for accessibility compliance, load the `accessibility-xl` skill for the full procedure and checklist.

**Quick reference — key non-negotiables in every design:**
- Text contrast: minimum **4.5:1** (3:1 for large text and UI components)
- Never use color as the only way to convey information — always pair with an icon or text label
- All interactive components must have **default, hover, focus, disabled, and checked** states defined
- Minimum touch target: **24×24 CSS pixels**
- All images must have appropriate alt text (or `alt=""` for decorative)
- Test in both **Light and Dark** mode

---

## Design System: XL Tourmaline

Xmartlabs maintains a shared design system called **Tourmaline** used as a starting base across client projects. Each project adapts it to its own visual identity — colors, corner radius, spacing scales, and component styles will vary per product.

**What stays consistent across all projects:**

- All components must include all **functional states**: default, hover, focus, disabled, checked.
- Disabled states are functional, not just visual — they must be coded as disabled, not simply styled gray.
- Focus states must be explicitly designed (custom outline, glow, or border) and consistent throughout the system.
- Minimum touch target size: **24×24 CSS pixels** (aim for 44×44 when possible).
- Colors must always follow a **semantic token system** — never use raw hex values directly in components. Tokens define roles (primary, danger, surface, etc.) and the specific values per project are defined in the design system setup phase.
- Feedback colors (success, warning, danger, info) must never be used for decoration — only for their semantic purpose, and always paired with an icon or text label, never color alone.
- Xmartlabs uses **Lucide Icons** as the standard icon set across projects.

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

Once the visual style is validated, work with the dev team to structure it into a design system. This means defining the foundations (color tokens, typography, grid, spacing, shadows) specific to this project — each product has its own values. Audit which components Tourmaline already covers and identify what needs to be created or customized. Always align with the dev team on the technical stack before building components — the framework's available components shape what needs to be designed from scratch.

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

1. **Follow the process** — every project goes through the 8 stages: Discovery → Research → UX Design → Branding → UI Design → Handoff → Support → Evolution.
2. **Design system compliance** — every component must be in Tourmaline or follow its patterns; all states (default, hover, focus, disabled, checked) must be defined.
3. **Accessibility** — use the `accessibility-xl` skill for the full WCAG 2.2 AA checklist before finalizing any design.
4. **Handoff completeness** — don't leave edge cases, empty states, or animations for devs to improvise. Define them in Figma before handoff.
5. **QA collaboration** — involve QA from design review through prototype validation. Use the 5-step QA ↔ Designer workflow.
6. **Lean mindset** — scope is flexible, timeline and objective are fixed. Think about what the product should *not* do.

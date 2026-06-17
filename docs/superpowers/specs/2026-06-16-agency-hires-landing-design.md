# Agency Hires Landing Page — Design Spec

**Date:** 2026-06-16  
**Repo:** `deaballe/deaballe.github.io`  
**URL:** https://deaballe.github.io  
**Status:** Approved for implementation

---

## Purpose

Single-page landing site for Andrea Balle's Agency Hires job application. Presents portfolio highlights, operational insight (Free The Founder), and contact information in a narrative flow — not as numbered form responses.

Built with AI tools in under a day (satisfies application question #2 once published).

---

## Decisions Log

| Topic | Decision |
|-------|----------|
| Hosting | GitHub Pages via `deaballe.github.io` repo |
| Visual identity | Photo palette: forest green + cream + red CTA + geometric shawl pattern |
| Language | English throughout |
| Structure | Narrative flow with natural section titles |
| Section 2 (AI build) | Reserved minimal placeholder, ready to fill later |
| Hero tagline | `Operations · Knowledge Systems · Workflow Scaling` |
| Navigation | Links in hero only — no sticky/fixed navbar |
| Hero bio | Short version (see Content section) |
| Tech stack | Static HTML + CSS + minimal JS (smooth scroll) |

---

## Visual Identity

### Color Palette

| Token | Hex | Usage |
|-------|-----|-------|
| `--green` | `#2D4A3E` | Primary background, hero, alternating sections |
| `--green-dark` | `#1E3329` | Gradients, footer, depth |
| `--cream` | `#F5F0E8` | Text on green backgrounds, light section backgrounds |
| `--cream-muted` | `#E8E0D4` | Cards, subtle borders |
| `--red` | `#C41E3A` | Primary CTAs, link hover accents |
| `--charcoal` | `#1A1A1A` | Body text on cream backgrounds |

### Pattern

SVG tile inspired by the shawl: stepped diamond with cross motif in center. Used as:

- Background texture at ~8% opacity on green sections
- Decorative divider band between major sections

File: `assets/pattern.svg` (inline or referenced).

### Typography

- **Headings:** Playfair Display (Google Fonts) — serif, elegant
- **Body / nav / labels:** Source Sans 3 or Inter (Google Fonts) — clean sans-serif
- **Tagline:** All-caps, letter-spacing ~0.15em, small size, prefixed with `✦`

### UI Components

- **Primary button / CTA:** Solid red background, cream text, rounded corners (~6px)
- **Secondary link:** Charcoal or cream text with red underline on hover
- **Photo:** Rounded corners (~12px), subtle box-shadow, no heavy border
- **Cards:** Cream-muted background, soft shadow, red "View →" link

---

## Page Structure

Single HTML page (`index.html`) with five content areas plus footer.

```
┌─────────────────────────────────────────┐
│ HERO (green)                            │
│  logo + nav links                       │
│  tagline + name + bio  │  photo          │
├─────────────────────────────────────────┤
│ WORK I'M PROUD OF (cream)               │
│  3 project cards                        │
├─────────────────────────────────────────┤
│ BUILT WITH AI (green)                   │
│  placeholder text                       │
├─────────────────────────────────────────┤
│ WHY FREE THE FOUNDER (cream)            │
│  connection + first week                │
├─────────────────────────────────────────┤
│ GET IN TOUCH (green-dark)               │
│  email + social links                   │
├─────────────────────────────────────────┤
│ FOOTER                                  │
└─────────────────────────────────────────┘
```

### Responsive Behavior

- **Desktop (≥768px):** Two-column hero; three project cards in a row
- **Mobile (<768px):** Single column; photo above or below text (photo first for visual impact); cards stack vertically
- Fluid typography using `clamp()` for heading sizes

---

## Content

### Hero

**Logo:** `A.Balle`

**Nav links (anchor, hero only):**
- About → `#about` (hero itself or scroll to top)
- Work → `#work`
- AI Build → `#ai-build`
- Insight → `#insight`
- Contact → `#contact`

**Tagline:**
```
✦ OPERATIONS · KNOWLEDGE SYSTEMS · WORKFLOW SCALING
```

**Name:** Andrea Balle

**Bio:**
> Operations-focused leader with research in knowledge management and hands-on experience scaling delivery systems. I map how knowledge flows first — then build workflows that hold up at scale.

**Photo:** User-provided portrait (`assets/photo.jpg`). Alt text: `Andrea Balle`.

---

### Section: Work I'm Proud Of

**ID:** `#work`  
**Background:** cream

Three cards:

#### 1. Comida Invisível — Invisible Food

- **Link:** https://app.comidainvisivel.com.br/
- **Description:** Among my responsibilities, I led the Verra certification process, which was approved with zero modifications.
- **CTA:** View →

#### 2. Academic Production

- **Link:** https://scholar.google.com/citations?hl=pt-BR&user=KBEnzrEAAAAJ&view_op=list_works
- **Description:** Multiple publications in international peer-reviewed journals focused on management.
- **CTA:** View →

#### 3. Mozilla Firefox

- **Link:** https://www.mozilla.org/credits/
- **Description:** Contributor — search my name on the credits page.
- **CTA:** View →

All external links open in new tab with `rel="noopener noreferrer"`.

---

### Section: Built with AI

**ID:** `#ai-build`  
**Background:** green with pattern texture

**Placeholder (until user provides final content):**
> This section is being finalized — check back soon.

Design: centered, italic or muted cream text, no "under construction" imagery. Section must remain visually present and styled consistently so adding content later is a text/link swap only.

**Future content (TBD by user):** Link to this landing page itself or another AI-built artifact, plus one-line description.

---

### Section: Why Free The Founder

**ID:** `#insight`  
**Background:** cream

Two subsections with subheadings:

#### Connection

> I looked up Free The Founder because your focus on scaling workflow systems deeply connects with my published research in the Journal of Knowledge Management on how knowledge sharing drives team performance. In my previous role at FAST Soluções Tecnológicas I applied these concepts to orchestrate an operational turnaround for a mature software platform where workflow research and systematic validation doubled team output and reduced bugs by thirty percent. I truly believe that institutional knowledge is the essential foundation for any automation which is why I analyze it first to ensure the underlying processes are completely solid.

#### My First Week

> During my first week I would love to support your operational vision by mapping out the knowledge flows within your current delivery templates to help identify hidden bottlenecks or single points of failure. Drawing from my experience with Lean and Scrum frameworks I would focus on auditing these data validation steps to see where we can protect the system from friction. My goal is to collaborate with your established structure and provide actionable insights that help your automated workflows scale smoothly for your clients.

---

### Section: Get in Touch

**ID:** `#contact`  
**Background:** green-dark

| Label | URL |
|-------|-----|
| Email | mailto:arballe@gmail.com |
| LinkedIn | https://www.linkedin.com/in/andreaballe/ |
| GitHub | https://github.com/deaballe |
| Google Scholar | https://scholar.google.com/citations?hl=pt-BR&user=KBEnzrEAAAAJ&view_op=list_works |

Display as a clean vertical list or horizontal row of links with icons (optional inline SVG, no external icon library required).

---

### Footer

```
© 2026 Andrea Balle
```

Small, centered, cream text at reduced opacity.

---

## File Structure

```
deaballe.github.io/
├── index.html
├── css/
│   └── styles.css
├── assets/
│   ├── photo.jpg
│   └── pattern.svg
├── docs/
│   └── superpowers/
│       └── specs/
│           └── 2026-06-16-agency-hires-landing-design.md
└── README.md
```

No build step. GitHub Pages serves static files from root on `main` branch.

---

## JavaScript

Minimal inline or single `js/main.js`:

- Smooth scroll for anchor links (`scroll-behavior: smooth` in CSS is sufficient; JS only if needed for offset)
- No frameworks, no dependencies

---

## Accessibility

- Semantic HTML5: `<header>`, `<main>`, `<section>`, `<footer>`, `<nav>`
- One `<h1>` (Andrea Balle) per page
- Section headings as `<h2>`, subsections as `<h3>`
- Sufficient color contrast (cream on green, charcoal on cream, red CTAs with cream text)
- `alt` on photo
- Focus styles on links and interactive elements
- `lang="en"` on `<html>`

---

## SEO / Meta

```html
<title>Andrea Balle — Operations · Knowledge Systems · Workflow Scaling</title>
<meta name="description" content="Operations-focused leader with research in knowledge management and hands-on experience scaling delivery systems.">
<meta name="viewport" content="width=device-width, initial-scale=1">
```

Optional Open Graph tags using photo and name (nice-to-have, not blocking).

---

## Out of Scope

- Blog, CMS, or multi-page navigation
- Analytics (can add later)
- Contact form (email link only)
- Dark mode toggle
- i18n / Portuguese version
- Section 2 final content (user will provide later)

---

## Implementation Checklist

- [ ] Copy user photo to `assets/photo.jpg`
- [ ] Create `assets/pattern.svg` (geometric shawl motif)
- [ ] Build `index.html` with all sections and content
- [ ] Build `css/styles.css` with palette, typography, responsive layout
- [ ] Add smooth scroll for nav links
- [ ] Verify locally in browser
- [ ] Push to `main` → confirm live at https://deaballe.github.io
- [ ] Update Section 2 placeholder when user provides content

---

## Self-Review Notes

- No TBD placeholders except Section 2 content (explicitly deferred by user)
- All four application topics covered: work portfolio (§Work), AI build (§Built with AI placeholder), Free The Founder (§Insight), contacts (§Contact)
- Architecture matches GitHub Pages constraints (static, no build)
- Scope is single-page, single implementation unit — no decomposition needed

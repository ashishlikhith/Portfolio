---
name: portfolio-frontend
description: Create bright, clean, and professional frontend UI for portfolio websites, personal sites, and showcase pages. Use this skill whenever the user wants to build a portfolio, personal website, project showcase, resume page, about-me page, or any personal branding frontend. Trigger for requests like "make my portfolio", "build a personal site", "create a showcase page", "design a clean portfolio UI", or any request combining professional presentation with personal or project content. Always use this skill for portfolio-related frontend work — even if the user only mentions "clean UI", "professional layout", or "neat design" in a personal context.
---
 
# Portfolio Frontend Skill
 
This skill guides the creation of bright, clean, and professional portfolio UIs — the kind that make a strong first impression on recruiters, clients, and collaborators.
 
## Design Philosophy
 
Portfolio UIs must balance **personality** with **professionalism**. The goal:
- **Bright** — light backgrounds, good contrast, energetic accents (not dark/moody)
- **Clean** — generous whitespace, clear visual hierarchy, no clutter
- **Professional** — consistent spacing, polished typography, structured layout
- **Memorable** — one signature design detail that sets it apart
 
> Think: a well-designed resume brought to life on the web.
 
---
 
## Before Writing Code
 
Ask yourself (or the user):
1. **Who are they?** Developer, designer, photographer, writer, student?
2. **What's the primary goal?** Get hired, attract clients, share work, showcase projects?
3. **What sections are needed?** Hero, About, Skills, Projects, Experience, Contact?
4. **Any color or font preferences?** Otherwise, choose something bright and distinctive.
 
---
 
## Visual Design System
 
### Color Palette — Bright & Professional
Use a **light base** with a **bold accent**. Examples:
 
| Scheme | Background | Text | Accent |
|--------|-----------|------|--------|
| Crisp White + Blue | `#FFFFFF / #F8FAFC` | `#1A1A2E` | `#2563EB` |
| Warm Ivory + Teal | `#FAFAF7 / #F5F0E8` | `#1C1C1C` | `#0D9488` |
| Soft Gray + Violet | `#F9F9FB / #F3F4F6` | `#111827` | `#7C3AED` |
| Pure White + Coral | `#FFFFFF / #FFF7F5` | `#1F2937` | `#E85D4A` |
 
**Rules:**
- Background: near-white or very light tint (never pure gray)
- Primary text: near-black (not pure `#000000`)
- Accent: one bold color used consistently for CTAs, highlights, borders
- Never use more than 2 accent colors
 
### Typography
Avoid generic fonts (Inter, Roboto, Arial). Choose pairs with character:
 
| Display / Heading | Body |
|-------------------|------|
| `Playfair Display` | `DM Sans` |
| `Syne` | `Epilogue` |
| `Cabinet Grotesk` | `Plus Jakarta Sans` |
| `Fraunces` | `General Sans` |
| `Clash Display` | `Satoshi` |
 
Load from Google Fonts. Use:
- Heading: bold weight (700–800), tight letter-spacing (`-0.02em`)
- Body: regular weight (400–500), comfortable line-height (`1.6–1.75`)
- Labels/tags: uppercase, tracked (`0.08em`), small size
 
### Spacing & Layout
- Max content width: `1100px–1200px`
- Section padding: `80px–120px` vertical
- Consistent spacing scale: `8 / 16 / 24 / 32 / 48 / 64 / 96px`
- Grid: CSS Grid for project cards, Flexbox for nav/hero
- Mobile-first, fully responsive
 
---
 
## Section Blueprints
 
### 1. Navigation
- Sticky on scroll with subtle `backdrop-filter: blur`
- Logo/name left, nav links right
- Active link uses accent color underline or dot
- Hamburger menu on mobile
 
### 2. Hero
- Full viewport height or tall (min `90vh`)
- Large name + short punchy tagline (1 line)
- Role/title in accent color or smaller weight
- One CTA button ("View Work" / "Download CV")
- Optional: subtle background pattern, floating shapes, or gradient mesh
- Entrance animation: fade-up stagger on name, tagline, CTA
 
### 3. About
- Two-column: text left, image/graphic right (or centered single column)
- 2–3 short paragraphs — personal, direct
- Optional: stat highlights (years exp, projects, etc.)
 
### 4. Skills
- Clean tag-cloud or grouped grid (by category)
- Skill pills with accent border or background tint
- No percentage bars — they look outdated
 
### 5. Projects (most important section)
- Card grid: 2–3 columns desktop, 1–2 tablet, 1 mobile
- Each card: project image/mockup, title, tech stack tags, short description, links
- Hover: subtle lift (`translateY(-4px)`) + shadow deepening
- Optional: filter by category (All / Web / Mobile / etc.)
 
### 6. Experience / Timeline
- Clean vertical timeline
- Company, role, dates, bullet achievements
- Accent line on the left, dots at each entry
 
### 7. Contact
- Simple and approachable
- Short invite text ("Let's build something together")
- Email link + social icons (GitHub, LinkedIn, Twitter)
- Optional: small inline form
 
### 8. Footer
- Minimal: name, copyright, social links
- Optional tagline
 
---
 
## Interactions & Animation
 
Keep animations **subtle and purposeful**:
 
```css
/* Scroll-triggered fade-up — apply to sections */
.reveal {
  opacity: 0;
  transform: translateY(24px);
  transition: opacity 0.6s ease, transform 0.6s ease;
}
.reveal.visible {
  opacity: 1;
  transform: translateY(0);
}
```
 
```js
// Intersection Observer for scroll reveals
const observer = new IntersectionObserver((entries) => {
  entries.forEach(e => e.isIntersecting && e.target.classList.add('visible'));
}, { threshold: 0.1 });
document.querySelectorAll('.reveal').forEach(el => observer.observe(el));
```
 
Other interactions:
- **Nav**: smooth scroll to sections
- **Cards**: hover lift + shadow
- **Buttons**: subtle scale (`1.02`) + accent shadow on hover
- **Links**: underline slide-in on hover
 
---
 
## Code Quality Standards
 
- Semantic HTML5 (`<header>`, `<main>`, `<section>`, `<article>`, `<footer>`)
- CSS custom properties for all colors, fonts, spacing
- Mobile-first media queries
- `alt` text on all images
- `aria-label` on icon-only buttons
- Smooth scroll: `html { scroll-behavior: smooth; }`
- Preload Google Fonts with `<link rel="preconnect">`
 
---
 
## Output Format
 
Default to a **single HTML file** with embedded CSS and JS unless the user asks for React or separate files. Structure:
 
```
index.html
├── <head> — fonts, meta, styles
├── <nav> — sticky navigation
├── <main>
│   ├── #hero
│   ├── #about
│   ├── #skills
│   ├── #projects
│   ├── #experience (optional)
│   └── #contact
└── <footer>
    └── <script> — scroll animations, mobile nav
```
 
---
 
## Quick Checklist Before Delivering
 
- [ ] Bright, light color palette with one bold accent
- [ ] Distinctive font pairing (not Inter/Roboto/Arial)
- [ ] Consistent spacing and max-width container
- [ ] Hero has name, role, and one CTA
- [ ] Projects section is the visual centerpiece
- [ ] Hover states on all interactive elements
- [ ] Scroll reveal animations on sections
- [ ] Fully responsive (mobile + tablet + desktop)
- [ ] Semantic HTML with accessibility basics
- [ ] No clutter — every element earns its place
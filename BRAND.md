# vercher.dev — Brand Usage Guide (v1.4)

**Changelog**
- v1.4: Clarified identity vs accent color semantics, strengthened Personal mode guardrails, and documented visual dominance rules.

## 1. Core Principle (Non-Negotiable)

**One symbol. Three modes. Zero improvisation.**

- The pixel “V” mark never changes shape.
- Meaning is communicated through **color + context only**.
- Typography, spacing, and layout remain consistent across all uses.

If the symbol changes shape, the system is broken.

All pages must support both light and dark mode.  
Brand modes define color relationships, not fixed themes.  
Light and dark mode switch background and text surfaces only — never brand colors.

---

## 2. Brand Modes & When to Use Them

Each brand mode defines exactly one identity color and one secondary identity / accent color.  
Accents support hierarchy and interaction but must never compete with the identity.

### A. Civic / Political Mode

**Identity Color:** Royal Blue  
**Secondary Identity / Accent Color:** Firebrick Red  
**Purpose:** Trust, legitimacy, civic clarity

**Use this mode when:**
- Content relates to city council, commissions, boards, or governance
- Public-facing community communication
- Materials that may be printed or shared offline
- Pages intended for broad, non-technical audiences

**Rules**
- Neither identity nor accent colors should be used as full backgrounds or allowed to visually dominate; they function as signals, not surfaces.
- Royal Blue is an **accent**, not a full background
- Primary backgrounds: charcoal (dark mode), light gray (light mode)
- Icon color: Royal Blue
- Red is allowed only as an accent (never dominant)
- SVGs must be **CSS-controlled** (no baked-in color)
- Vercher **name must be more visually prominent than the icon**
- The header lockup uses a subtle outline for readability on light backgrounds
- The icon functions as a *seal*, not the headline

**Avoid**
- Experimental layouts
- Technical jargon near the mark
- Over-stylization

*Mental model:* boring on purpose, credible by default

---

### B. Consulting Mode

**Identity Color:** Cadmium Yellow  
**Secondary Identity / Accent Color:** Ultramarine Blue  
**Purpose:** Signal competence, systems thinking, and confidence

**Use this mode when:**
- Promoting consulting services
- Case studies or project writeups
- Professional bios, proposals, decks
- Anything revenue-adjacent

**Rules**
- Ultramarine Blue may carry more visual weight in layouts, but Cadmium Yellow defines identity and emphasis.
- Neither identity nor accent colors should be used as full backgrounds or allowed to visually dominate.
- Cadmium Yellow and Ultramarine Blue are **accent**, not a full background
- Primary backgrounds: charcoal (dark mode), light gray (light mode)
- Icon color: Cadmium Yellow 
- Icon may stand alone without your name in digital contexts
- SVGs must be **CSS-controlled** (no baked-in color)
- The header lockup uses a subtle outline for readability on light backgrounds

**Avoid**
- Red or blue tones (political bleed)
- Softened or pastel yellow variants
- Decorative effects that compete with the geometry

*Mental model:* quietly sharp, not loud

---

### C. Personal Mode

**Identity Color:** Violet  
**Secondary Identity / Accent Color:** Ultramarine Blue  
**Purpose:** Curiosity, reflection, individuality

**Use this mode when:**
- Blogging or essays
- Personal experiments or side projects
- Exploratory or reflective writing

**Rules**
- Violet may be primary or accent
- Ultramarine Blue is an **accent**, not a full background
- Layouts may be more expressive, but typography should remain consistent with the rest of the site unless a specific deviation is intentional and justified.
- Icon may be paired with slightly lighter or more human typography, but novelty fonts and decorative scripts remain prohibited.
- Minor asymmetry is acceptable
- The header lockup follows the same CSS-driven structure as other modes
- Expressive does not mean experimental: gradients, political color palettes, and dominant brand-color backgrounds are still prohibited.

**Avoid**
- Corporate polish
- Political color palettes
- Sales-oriented framing

*Mental model:* human first, system second

---

## 3. Brand Color Tokens

### Civic / Political Mode
- Royal Blue: `#2222B2`
- Firebrick Red (accent): `#B22222`
- Light Gray (light background): `#e9ebf2`
- Light Gray (light text): `#e9ebf2`
- Charcoal (dark background): `#1e1e1e`
- Soft Black (dark text): `#121212`

### Consulting Mode
- Cadmium Yellow: `#FFF600`
- Ultramarine Blue (accent): `#0009FF`
- Light Gray (light background): `#e9ebf2`
- Light Gray (light text): `#e9ebf2`
- Charcoal (dark background): `#1e1e1e`
- Soft Black (dark text): `#121212`

### Personal Mode
- Violet: `#6A0DAD`
- Ultramarine Blue (accent): `#0009FF`
- Light Gray (light background): `#e9ebf2`
- Light Gray (light text): `#e9ebf2`
- Charcoal (dark background): `#1e1e1e`
- Soft Black (dark text): `#121212`

---

## 4. Favicon Usage (Per-Mode Locking)

Favicons are page-level metadata and are not styled by CSS variables.  
Each page MUST explicitly select the favicon that matches its brand mode.

### Required Favicons
- Civic / Political: `favicon-civic.svg` (Royal Blue)
- Consulting: `favicon-consulting.svg` (Cadmium Yellow)
- Personal: `favicon-personal.svg` (Violet)

### Rules
- Geometry must be identical across all favicons
- Color is the only permitted difference
- Favicon selection must match the page’s brand mode
- Favicons are set once per page (or layout) and never overridden

### Examples

Civic / Political page:
```html
<link rel="icon" href="/favicon-civic.svg">
<body data-brand-mode="civic">
```

Consulting page:
```html
<link rel="icon" href="/favicon-consulting.svg">
<body data-brand-mode="consulting">
```

Personal page:
```html
<link rel="icon" href="/favicon-personal.svg">
<body data-brand-mode="personal">
```

If a page’s favicon and brand mode do not match, the page is considered invalid.

---


## 5. Implementation Checklist

Every new page added to vercher.dev MUST satisfy the following checklist before it is considered complete.

### Page-Level Requirements
- Exactly one `data-brand-mode` attribute is set on the `<body>` element
- The selected brand mode matches the page’s intent and audience
- A matching favicon is explicitly declared in the `<head>`

### Visual & Brand Enforcement
- All brand colors are applied via CSS variables (no hard-coded hex values in components)
- SVG icons use `currentColor` or CSS-controlled `fill`
- No mixing of brand modes within a single page

### Content Alignment
- Tone and language match the selected brand mode
- Civic pages prioritize clarity and trust
- Consulting pages prioritize competence and outcomes
- Personal pages prioritize reflection and exploration

### Validation
- Page renders correctly in light and dark mode
- Favicon is correct at 16px and 32px
- Visual scan confirms the page “reads” as a single mode

If any checklist item fails, the page is not ready to publish.

## 6. Comment Block Template

Every new HTML page SHOULD begin with a standardized comment block.  
This block documents intent, enforces discipline, and reduces future drift.

### Standard Template

```html
<!--
Page:
URL:

Brand Mode: civic | consulting | personal
Favicon:

Intent:
- What this page exists to do
- Who it is for

Checklist:
- [ ] data-brand-mode matches brand mode
- [ ] Correct favicon set in <head>
- [ ] Uses brand.css tokens only
- [ ] Icons use CSS-controlled fill
- [ ] Page reads as a single mode

Last Reviewed: YYYY-MM-DD
-->
```

### Usage Notes
- This block has no runtime effect
- It exists to slow down decisions before content is written
- It should be completed before the page is considered publishable
- Updating the `Last Reviewed` date is encouraged when changes are made

## 7. Icon Usage Rules (Hard Constraints)

### Approved Variants
- Icon-only
- Horizontal lockup
- CSS-controlled SVG only

### Spacing
- Minimum clear space: **1× the pixel unit**
- Never crowd text or UI controls
- On mobile, padding must exceed icon size

### Size Constraints
- ≥ 24px: standard icon
- ≤ 24px: micro variant recommended
- Favicon usage must be tested at 16px and 32px

---

## 8. Color Rules (No Exceptions)

- One primary brand color per page
- Neutral colors are always permitted
- Never mix:
  - Cadmium Yellow with political colors
  - Violet with political colors
- Dark mode flips background only — **never the brand color**

If a page feels like it belongs to two modes, the wrong mode was chosen.

---

## 9. Typography Relationship

- Icon: geometric, rigid, modular
- Type: readable, human, restrained
- Never pair the icon with novelty fonts
- Civic pages bias toward clarity
- Personal pages may allow softness

---

## 10. Governance Rule (This Prevents Drift)

When uncertain:
1. Who is this for?
2. What is the risk if this feels wrong?
3. Choose the most conservative applicable mode

**Tie-breakers**
- Public-facing + ambiguous → Civic mode
- Revenue-related → Consulting mode
- Exploratory → Personal mode

---

## 11. Versioning

This document is versioned intentionally.

Changes require:
- A new version number
- Explicit rationale
- No ad-hoc tweaks

Future clarity beats present convenience.

When versions are bumped, a short changelog (1–2 bullets) should be added at the top of this document to summarize intent.
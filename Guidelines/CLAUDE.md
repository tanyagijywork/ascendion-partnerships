# ASCENDION — DESIGN SYSTEM & BUILD RULES


## DESIGN RULES

### 1. COLOR SYSTEM

#### Primitive Tokens
> Source of truth: Figma file `Ascendion-2.0` → UI Kit → Colours → Colour Primitive

| Token | Hex | Figma name | Usage |
|-------|-----|------------|-------|
| `--primary-500` | `#6464d7` | primary/500 | Brand violet — CTAs on light bg, accents, active states |
| `--primary-100` | `#968cfa` | primary/100 | Light violet — rarely used |
| `--primary-900` | `#5a37af` | primary/900 | Dark violet — hover states |
| `--accent-100` | `#2ddcaa` | accent/100 | Teal — CTAs on dark bg, highlights, live indicators |
| `--accent-500` | `#009673` | accent/500 | Dark teal — hover on accent buttons |
| `--accent-900` | `#006450` | accent/900 | Darkest teal — use sparingly |
| `--neutral-0` | `#ffffff` | neutral/0 | White |
| `--neutral-100` | `#f4f4f4` | neutral/100 | Off-white / subtle bg (slight warm tint in Figma) |
| `--neutral-200` | `#e3e2df` | neutral/200 | Secondary text on dark bg, warm light border |
| `--neutral-300` | `#aaaaaa` | neutral/300 | Disabled border |
| `--neutral-400` | `#999999` | neutral/400 | Separator, default border |
| `--neutral-500` | `#808080` | neutral/500 | Mid-tone — use sparingly |
| `--neutral-600` | `#4b4b4b` | neutral/600 | Disabled text, mid-dark |
| `--neutral-700` | `#333333` | neutral/700 | Secondary text |
| `--neutral-800` | `#1a1a1a` | neutral/800 | Dark subtle bg |
| `--neutral-900` | `#000000` | neutral/900 | Black |
| `--secondary-yellow` | `#ffc30f` | secondary/yellow-500 | Terminal highlight only |
| `--secondary-pink` | `#f50f7d` | secondary/pink-500 | Accent use only — not for general UI |

> **Note on neutrals:** Figma neutral/200 (`#e3e2df`) and neutral/100 (`#f4f4f4`) carry a slight warm tint. Use exact Figma hex values in code — do not substitute with pure grays.

#### Semantic Tokens
| Token | Value | Usage |
|-------|-------|-------|
| `--bg-default` | `#ffffff` | White sections |
| `--bg-subtle` | `#f4f4f4` | Nav bar, pillar section, card backgrounds |
| `--bg-dark` | `#000000` | Hero, services, stats, CTA sections |
| `--bg-dark-subtle` | `#1a1a1a` | Announce bar, AAVA section, dark card bg |
| `--bg-dark-2` | `#333333` | Terminal bg, AAVA capability chips |
| `--bg-violet` | `#6464d7` | Announce badge, violet accent panels |
| `--bg-accent` | `#2ddcaa` | Accent panels only |
| `--text-primary` | `#000000` | Body text on white |
| `--text-secondary` | `#333333` | Subtext on white |
| `--text-inv` | `#ffffff` | All text on dark backgrounds |
| `--text-inv-2` | `#e3e2df` | Secondary text on dark backgrounds (neutral/200) |
| `--text-highlight` | `#6464d7` | Labels on white backgrounds |
| `--text-hi-inv` | `#2ddcaa` | Labels on dark backgrounds |
| `--text-disabled` | `#4b4b4b` | Disabled / metadata text (neutral/600) |
| `--border` | `#999999` | Default border (neutral/400) |
| `--border-separator` | `#e3e2df` | Subtle separator on light bg (neutral/200) |

**NEVER invent colors. Only use the tokens above.**

---

### 2. TYPOGRAPHY SYSTEM

#### Fonts
```css
--font-display: 'PP Neue Machina', sans-serif;  /* H1, H2, H3, stats, hero */
--font-primary: 'Inter', sans-serif;             /* H4, H5, body, labels, UI */
--font-mono:    'Roboto Mono', monospace;         /* Terminal, code, badges */
```

**PP Neue Machina** is a self-hosted font (not on Google Fonts). Load via `@font-face` from `../assets/fonts/`. Inter loads from Google Fonts:
```html
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&display=swap" rel="stylesheet">
```

**PP Neue Machina** is used for all display text — Display, H1 through H3, stat numbers, and hero headlines. **Inter** is used for all UI text — H4, H5, body copy, labels, nav, buttons, footer.

> **Inter weight names in Figma:** Use `"Regular"` (400), `"Semi Bold"` (600 — note the space), `"Medium"` (500). Do NOT use `"SemiBold"` (no space) — it will fail to load.
> **PP Neue Machina weight name in Figma:** `"Plain Regular"` (400).

#### Type Scale — Desktop (default)
> Source of truth: Figma `Responsive` variable collection, Desktop mode

| Role | Figma name | Font | Size | Line-height | Weight | Notes |
|------|-----------|------|------|-------------|--------|-------|
| Display L | `dis - l` | PP Neue Machina | **72px** | **80px** | 400 | Hero-scale headlines only |
| Stats L | `stats - l` | PP Neue Machina | **64px** | **72px** | 400 | Large stat numbers |
| Stats M | `stats - M` | PP Neue Machina | **48px** | **56px** | 400 | Medium stat numbers |
| H1 | `h1` | PP Neue Machina | **48px** | **52px** | 400 | Page / section headings |
| H2 | `h2` | PP Neue Machina | **40px** | **48px** | 400 | Sub-section headings |
| H3 | `h3` | PP Neue Machina | **32px** | **40px** | 400 | Card titles |
| H4 | `h4` | Inter | **24px** | **28px** | 400 | Feature headings, accordion titles |
| H5 | `h5` | Inter | **20px** | **26px** | 400 | Small headings, card subtitles |
| Body XXL | `body - xxl` | PP Neue Machina | **32px** | **39px** | 400 | Large intro / lead copy |
| Body XL | `body - xl` | Inter | **24px** | **29px** | 400 / Semi Bold | Section sub-leads |
| Body L | `body - l` | Inter | **20px** | **26px** | 400 / Semi Bold | Lead paragraphs |
| Body M | `body - m` | Inter | **16px** | **24px** | 400 | Standard body copy |
| Body S | `body - s` | Inter | **14px** | **16px** | 400 | Card descriptions, captions |
| Label M | `label - m` | Inter | **16px** | **18px** | 500 | Uppercase section labels |
| Label S | `label - s` | Inter | **14px** | **16px** | 500 | Compact uppercase labels |
| Button M | `button - m` | Inter | **16px** | **18px** | 500 | Desktop button text |
| Nav link | — | Inter | 16px | — | 400 | — |
| Footer col head | — | Inter | 12px | — | 700 | Uppercase, 0.1em tracking |
| Footer link | — | Inter | 14px | 1.4 | 400 | — |
| Tag / badge | — | Inter | 11px | — | 700 | Uppercase, 0.1em tracking |
| Mono code | — | Roboto Mono | 13px | 2 | 400 | Terminal only |

#### Responsive Type Scale
> Figma `Responsive` collection — three modes: Desktop / Tab / Mobile

| Role | Desktop | Tab | Mobile | Desktop LH | Tab LH | Mobile LH |
|------|---------|-----|--------|-----------|--------|-----------|
| Display L | 72px | 64px | 48px | 80px | 72px | 56px |
| Stats L | 64px | 56px | 48px | 72px | 56px | 44px |
| Stats M | 48px | 44px | 48px | 56px | 56px | 44px |
| H1 | 48px | 40px | 36px | 52px | 48px | 48px |
| H2 | 40px | 32px | 36px | 48px | 44px | 36px |
| H3 | 32px | 28px | 24px | 40px | 32px | 24px |
| H4 | 24px | 20px | 18px | 28px | 24px | 16px |
| H5 | 20px | 18px | 16px | 26px | 24px | 24px |
| Body XXL | 32px | 28px | 22px | 39px | 36px | 28px |
| Body XL | 24px | 18px | 18px | 29px | 24px | 24px |
| Body L | 20px | 18px | 16px | 26px | 24px | 24px |
| Body M | 16px | 14px | 14px | 24px | 20px | 20px |
| Body S | 14px | 12px | 12px | 16px | 14px | 14px |
| Label M | 16px | 14px | 14px | 18px | 16px | 16px |
| Label S | 14px | 12px | 12px | 16px | 14px | 14px |
| Button | 16px | 14px | 14px | 18px | 16px | 16px |

---

### 3. LABEL STYLE (Section Labels above Headings)

Labels are **centered on the page** with a horizontal rule on each side — like a section divider. They always sit directly above section headings.

```
────────────────  LABEL TEXT  ────────────────
```

```css
.lbl {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 16px;
  font-size: 13px;
  font-weight: 500;
  letter-spacing: 0.12em;
  text-transform: uppercase;
  color: #2ddcaa;              /* teal — dark backgrounds */
  margin-bottom: 24px;
}
.lbl--dark {
  color: #6464d7;              /* violet — white/light backgrounds */
}
/* Ruled lines either side */
.lbl::before,
.lbl::after {
  content: '';
  flex: 1;
  height: 1px;
  background: currentColor;
  opacity: 0.3;
}
```

**Rules:**
- Every section heading MUST have a label above it
- Label is always **centered** with ruled lines — never left-aligned
- On dark backgrounds → `.lbl` (teal `#2ddcaa`)
- On white/light backgrounds → `.lbl.lbl--dark` (violet `#6464d7`)
- Lines use `currentColor` with `opacity: 0.3` — they always match the label text color
- `margin-bottom: 24px` (increased from 16px to account for centered layout)

---

### 4. SECTION SPACING

```css
:root {
  --px: 80px;   /* Horizontal padding */
  --py: 80px;   /* Vertical section padding (top + bottom) */
}

section { padding-top: var(--py); padding-bottom: var(--py); }

.container {
  max-width: 1440px;
  margin: 0 auto;
  padding-left: var(--px);
  padding-right: var(--px);
}

.s-head { margin-bottom: 56px; }   /* Space between heading block and content */
```

#### Responsive Breakpoints
| Breakpoint | `--px` | `--py` | Nav height |
|------------|--------|--------|------------|
| Default | 80px | 80px | 86px |
| ≤ 1200px | 60px | 80px | 86px |
| ≤ 900px | 32px | 60px | 64px |
| ≤ 600px | 24px | 48px | 64px |

---

### 5. MARGINS

- Section head to grid/content: `margin-bottom: 56px` on `.s-head`
- Label to heading: `margin-bottom: 16px` on `.lbl`
- Heading to body: `margin-top: 16px` on `.s-sub`
- Card internal padding: `40px 32px` (impact cards), `36px` (insight cards), `48px 36px` (case study), `40px 36px` (pillar cards)
- Grid gaps: `20px` (insights), `24px` (pillars), `80px` (footer columns)
- Button gap between stacked CTAs: `12px`

---

### 6. BACKGROUND ALTERNATING PATTERN

Pages must alternate section backgrounds in this order (matching the homepage):

| Section | Background | Text color |
|---------|-----------|------------|
| Announce Bar | `#1a1a1a` | Light |
| **Nav** | `#f4f4f4` | Dark |
| **Hero** | `#000000` | Light |
| Ticker bar | `#000000` | Light |
| **Real Impact / Stats** | `#ffffff` | Dark |
| **Services / What We Do** | `#000000` | Light |
| **AAVA / How We Deliver** | `#1a1a1a` | Light |
| **Three Pillars** | `#f4f4f4` | Dark |
| **Scale / Numbers** | `#000000` | Light |
| **Insights** | `#ffffff` | Dark |
| **Impact Now / Case Studies / CTA** | `#000000` | Light |
| **Footer** | `#ffffff` | Dark |

When building inner pages, use the same alternating dark/light pattern. Always start after the hero with a white section.

---

### 6b. SPACING & CORNER RADIUS TOKENS

> Source of truth: Figma `Alias` variable collection

#### Spacing scale (px)
`0 · 2 · 4 · 6 · 8 · 12 · 16 · 20 · 24 · 32 · 36 · 40 · 48 · 56 · 60 · 64 · 72 · 80 · 88 · 96 · 120 · 128 · 136 · 144`

Only use values from this list. Never invent arbitrary spacing values.

#### Corner radius scale
| Token name | Value | Usage |
|-----------|-------|-------|
| `Corner radius/0` | 0px | No rounding |
| `Corner radius/2` (XS) | **2px** | Standard for cards, buttons, chips, badges, panels |
| `Corner radius/4` (S) | 4px | — |
| `Corner radius/8` (M) | 8px | — |
| `Corner radius/16` (L) | 16px | — |
| `Corner radius/20` (XL) | 20px | — |
| `Corner radius/24` (XXL) | 24px | — |
| `Corner radius/40` (XXXL) | 40px | Nav control / circular buttons only |

**Rule:** `border-radius: 2px` (XS) for all cards, buttons, chips, and badges. Use `border-radius: 50%` ONLY for circular icon buttons (e.g. nav arrow controls). No other values unless explicitly specified.

---

### 7. HEADER RULES — MUST MATCH EXACTLY

```html
<!-- ANNOUNCE BAR (only on homepage) -->
<div class="announce">
  <span class="announce-tag">Ascendion × Everest</span>
  <span class="announce-text">[announcement text]</span>
  <a href="#" class="announce-link">
    Read the Report
    <svg width="14" height="14" viewBox="0 0 16 16" fill="none">
      <path d="M3 8h10M9 4l4 4-4 4" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
    </svg>
  </a>
</div>

<!-- NAV -->
<header class="nav" id="nav">
  <div class="container nav-inner">
    <a href="/" class="nav-logo" aria-label="Ascendion home">
      <span class="nav-logo-text">ASCENDION</span>
      <span class="nav-logo-tagline">Engineering to elevate life</span>
    </a>
    <nav class="nav-menu" aria-label="Main">
      <ul class="nav-links">
        <li>
          <a href="#" class="nav-link nav-link--aava">
            AAVA<sup>™</sup>
            <svg width="12" height="12" viewBox="0 0 16 16" fill="none" aria-hidden="true">
              <path d="M4 12L12 4M12 4H6M12 4v6" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>
          </a>
        </li>
        <li><a href="#" class="nav-link">What We Do <svg ...chevron/></a></li>
        <li><a href="#" class="nav-link">Who We Serve <svg ...chevron/></a></li>
        <li><a href="#" class="nav-link">How We Deliver <svg ...chevron/></a></li>
        <li><a href="#" class="nav-link">Insights &amp; Impact <svg ...chevron/></a></li>
        <li><a href="#" class="nav-link">Careers <svg ...chevron/></a></li>
      </ul>
      <a href="#" class="btn btn-primary">
        <span class="btn__label">Get In Touch</span>
        <span class="btn__icon" aria-hidden="true">
          <svg width="16" height="16" viewBox="0 0 16 16" fill="none">
            <path d="M3 8h10M9 4l4 4-4 4" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
          </svg>
        </span>
      </a>
    </nav>
    <button class="nav-toggle" id="navToggle" aria-label="Toggle menu" aria-expanded="false">
      <span></span><span></span><span></span>
    </button>
  </div>
</header>
```

**Nav CSS rules:**
- `position: sticky; top: 0; z-index: 200`
- Background: `#f4f4f4`
- Height: `86px`
- On scroll: `box-shadow: 0 1px 0 #cccccc`
- Logo wordmark: Inter 18px 800 weight, letter-spacing -0.03em, color `#000`
- Logo tagline: Inter 11px 400, color `#666666`, display block below wordmark
- Nav links: 16px 400, padding `6px 10px`, gap `4px`, hover color `#5a37af`
- Active link: color `#6464d7`
- CTA: `.btn-primary` — black bg, white text, teal arrow icon

**Nav link order (left to right):**
1. **AAVA™** — first link, always violet (`#6464d7`), uses external link icon ↗ (NOT a chevron), links to AAVA platform page. Class: `nav-link--aava`. The ™ is a `<sup>` element.
2. What We Do — has chevron dropdown
3. Who We Serve — has chevron dropdown (replaces "Industries")
4. How We Deliver — has chevron dropdown (replaces "Who We Are")
5. Insights & Impact — has chevron dropdown (replaces "Insights")
6. Careers — has chevron dropdown (was a plain link)

```css
/* AAVA link is always violet, never inherits hover color */
.nav-link--aava { color: #6464d7; font-weight: 500; }
.nav-link--aava:hover { color: #5a37af; }
.nav-link--aava sup { font-size: 10px; vertical-align: super; }
/* Logo tagline */
.nav-logo-tagline { display: block; font-size: 11px; font-weight: 400; color: #666666; letter-spacing: 0; line-height: 1.2; margin-top: 2px; }
```

**Current page nav link gets `.active` class (color `#6464d7`).**

---

### 8. FOOTER RULES — MUST MATCH EXACTLY

```html
<footer class="footer">
  <div class="container">
    <div class="footer-cols">
      <!-- Col 1: What We Do -->
      <div>
        <div class="footer-col-head">What We Do</div>
        <ul class="footer-links">
          <li><a href="#" class="footer-link">Applied AI</a></li>
          <li><a href="#" class="footer-link">GCC<sup>AI</sup></a></li>
          <li><a href="#" class="footer-link">Product<sup>AI</sup></a></li>
          <li><a href="#" class="footer-link">Data &amp; Insights<sup>AI</sup></a></li>
          <li><a href="#" class="footer-link">Salesforce Implementation</a></li>
          <li><a href="#" class="footer-link">Quality Engineering<sup>AI</sup></a></li>
          <li><a href="#" class="footer-link">Experience<sup>AI</sup></a></li>
          <li><a href="#" class="footer-link">Operations<sup>AI</sup></a></li>
          <li><a href="#" class="footer-link">AI Workforce Transformation</a></li>
          <li><a href="#" class="footer-link">Enterprise Platform</a></li>
          <li><a href="#" class="footer-link">Platform Engineering<sup>AI</sup></a></li>
        </ul>
      </div>
      <!-- Col 2: Industries -->
      <div>
        <div class="footer-col-head">Industries</div>
        <ul class="footer-links">
          <li><a href="#" class="footer-link">Banking &amp; Financial Services</a></li>
          <li><a href="#" class="footer-link">Communications, Media and Entertainment</a></li>
          <li><a href="#" class="footer-link">Healthcare &amp; Life Sciences</a></li>
          <li><a href="#" class="footer-link">Retail and Consumer Goods</a></li>
          <li><a href="#" class="footer-link">High-tech</a></li>
          <li><a href="#" class="footer-link">Travel and Hospitality</a></li>
        </ul>
      </div>
      <!-- Col 3: Who We Are -->
      <div>
        <div class="footer-col-head">Who We Are</div>
        <ul class="footer-links">
          <li><a href="#" class="footer-link">Leadership</a></li>
          <li><a href="#" class="footer-link">Analyst Recognition</a></li>
          <li><a href="#" class="footer-link">Certifications</a></li>
          <li><a href="#" class="footer-link">Locations</a></li>
          <li><a href="#" class="footer-link">ESG</a></li>
        </ul>
      </div>
      <!-- Col 4: Quick Links -->
      <div>
        <div class="footer-col-head">Quick Links</div>
        <ul class="footer-links">
          <li><a href="#" class="footer-link">Insights and impact</a></li>
          <li><a href="#" class="footer-link">Careers India</a></li>
          <li><a href="#" class="footer-link">Careers North America</a></li>
          <li><a href="#" class="footer-link">Careers Europe</a></li>
          <li><a href="#" class="footer-link">Careers Asia Pacific</a></li>
          <li><a href="#" class="footer-link">Global Delivery Hubs</a></li>
          <li><a href="#" class="footer-link">Contact us</a></li>
        </ul>
      </div>
      <!-- Col 5: Social icons — circular filled, stacked vertically, no heading -->
      <div style="padding-top:40px">
        <div class="footer-social">
          <a href="#" class="footer-social-link footer-social-link--linkedin" aria-label="LinkedIn">
            <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor">
              <path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/>
            </svg>
          </a>
          <a href="#" class="footer-social-link footer-social-link--youtube" aria-label="YouTube">
            <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor">
              <path d="M23.498 6.186a3.016 3.016 0 00-2.122-2.136C19.505 3.545 12 3.545 12 3.545s-7.505 0-9.377.505A3.017 3.017 0 00.502 6.186C0 8.07 0 12 0 12s0 3.93.502 5.814a3.016 3.016 0 002.122 2.136c1.871.505 9.376.505 9.376.505s7.505 0 9.377-.505a3.015 3.015 0 002.122-2.136C24 15.93 24 12 24 12s0-3.93-.502-5.814zM9.545 15.568V8.432L15.818 12l-6.273 3.568z"/>
            </svg>
          </a>
          <a href="#" class="footer-social-link footer-social-link--instagram" aria-label="Instagram">
            <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor">
              <path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z"/>
            </svg>
          </a>
        </div>
      </div>
    </div>
    <div class="footer-bottom">
      <span class="footer-copy">Copyright 2026, ASCENDION. All rights reserved.</span>
      <div class="footer-legal">
        <a href="#" class="footer-legal-link">Privacy Policy</a>
        <span class="footer-sep">|</span>
        <a href="#" class="footer-legal-link">Terms of Use</a>
        <span class="footer-sep">|</span>
        <a href="#" class="footer-legal-link">Accessibility Disclosure</a>
        <span class="footer-sep">|</span>
        <a href="#" class="footer-legal-link">AI-enhanced Content Notice</a>
        <span class="footer-sep">|</span>
        <a href="#" class="footer-legal-link">Security Disclosure Policy</a>
      </div>
    </div>
  </div>
</footer>
```

**Footer CSS rules:**
- Background: `#ffffff`
- Border-top: `1px solid #cccccc`
- Padding: `80px 0`
- Grid: `grid-template-columns: 2fr 2fr 1.5fr 1.5fr auto; gap: 80px`
- Column heads: 12px, 700, uppercase, letter-spacing 0.1em, color `#000`
- Links: 14px, color `#333`, hover `#5a37af`
- Superscript `<sup>AI</sup>`: font-size 9px, vertical-align super, color inherit
- Footer-bottom: flex, space-between, border-top `1px solid #cccccc`, padding-top `24px`

**Footer social icons (Col 5) — CIRCULAR with brand-color fills, stacked vertically:**
```css
.footer-social {
  display: flex;
  flex-direction: column;   /* stacked vertically */
  gap: 10px;
  align-items: flex-start;
}
.footer-social-link {
  width: 36px; height: 36px; border-radius: 50%;   /* CIRCULAR */
  display: flex; align-items: center; justify-content: center;
  color: #ffffff;
  transition: opacity 0.15s, transform 0.15s;
}
.footer-social-link:hover { opacity: 0.85; transform: translateY(-2px); }

/* Platform brand fills */
.footer-social-link--linkedin  { background: #0077b5; }
.footer-social-link--youtube   { background: #ff0000; }
.footer-social-link--instagram { background: linear-gradient(135deg, #f09433 0%, #e6683c 25%, #dc2743 50%, #cc2366 75%, #bc1888 100%); }
```
- Icons: SVG fill `currentColor` (white), 16×16px
- Platforms: **LinkedIn, YouTube, Instagram** (Twitter/X removed)
- Stacked **vertically** in Col 5 (not horizontally)
- **No text labels** — icon only, with `aria-label` for accessibility
- **No border** — solid filled circles only

---

### 9. BUTTON RULES

> Source of truth: Figma UI Kit → Buttons & Links section.
> Two sizes: **Medium** (desktop, 16px / padding `14px 20px`) and **Small** (Tab & Mobile, 14px / padding `10px 16px`).

#### Structure
Every button has three parts: **label** + **icon container**. The icon is always an arrow SVG, colored differently from the label text. On hover the icon slides right 3px.

```html
<!-- Light background button -->
<a class="btn btn-primary" href="#">
  <span class="btn__label">Get In Touch</span>
  <span class="btn__icon" aria-hidden="true">
    <svg viewBox="0 0 16 16" fill="none">
      <path d="M3 8h10M9 4l4 4-4 4" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
    </svg>
  </span>
</a>
```

```css
/* Base */
.btn {
  display: inline-flex;
  align-items: center;
  gap: 12px;
  font-family: var(--font-primary);
  font-size: 16px;
  font-weight: 500;
  letter-spacing: 0.02em;
  border-radius: 2px;
  padding: 14px 20px;
  line-height: 1;
  white-space: nowrap;
  cursor: pointer;
  transition: background 0.2s ease, color 0.2s ease, border-color 0.2s ease;
}

.btn__icon {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  transition: transform 0.2s ease;
  flex-shrink: 0;
}
.btn:hover .btn__icon { transform: translateX(3px); }
```

#### Button Variants

| Class | Background | Label color | Icon color | Hover bg |
|-------|-----------|------------|-----------|----------|
| `.btn-primary` | `#000000` | `#ffffff` | `#6464d7` | `#1a1a1a` |
| `.btn-inverse` | `#2ddcaa` | `#000000` | `#000000` | `#009673` |
| `.btn-ghost` | transparent | `#000000` | `#6464d7` | `#f4f4f4` |
| `.btn-ghost-inv` | transparent | `#ffffff` | `#2ddcaa` | `rgba(255,255,255,0.08)` |
| `.btn-text` | none | `#6464d7` | `#6464d7` | — (color `#5a37af`) |
| `.btn-text-inv` | none | `#2ddcaa` | `#2ddcaa` | — (color `#009673`) |

```css
.btn-primary        { background: #000; color: #fff; border: none; }
.btn-primary .btn__icon { color: #6464d7; }
.btn-primary:hover  { background: #1a1a1a; }

.btn-inverse        { background: #2ddcaa; color: #000; border: none; }
.btn-inverse .btn__icon { color: #000; }
.btn-inverse:hover  { background: #009673; }

.btn-ghost          { background: transparent; color: #000; border: 1px solid #000; }
.btn-ghost .btn__icon { color: #6464d7; }
.btn-ghost:hover    { background: #f4f4f4; }

.btn-ghost-inv      { background: transparent; color: #fff; border: 1px solid #fff; }
.btn-ghost-inv .btn__icon { color: #2ddcaa; } /* teal icon — confirmed in Figma Colour Semantics */
.btn-ghost-inv:hover { background: rgba(255,255,255,0.08); }

.btn-text           { background: none; color: #6464d7; padding: 0; }
.btn-text:hover     { color: #5a37af; }

.btn-text-inv       { background: none; color: #2ddcaa; padding: 0; }
.btn-text-inv:hover { color: #009673; }
```

**Small variant:** `.btn-sm` — font-size 14px, padding `10px 16px`

**Usage by context:**
- On light bg, primary CTA → `.btn-primary` (black bg, white text, violet icon)
- On light bg, secondary CTA → `.btn-ghost`
- On dark bg, primary CTA → `.btn-inverse` (teal bg, black text, black icon)
- On dark bg, secondary CTA → `.btn-ghost-inv`
- Inline text links → `.btn-text` or `.btn-text-inv`

---

### 10. ANIMATION RULES

All animation rules are sourced from `animation.html`.

#### Scroll Reveal
```css
.rv {
  opacity: 0;
  transform: translateY(24px);
  transition: opacity 0.7s ease-in-out, transform 0.7s ease-in-out;
}
.rv.in { opacity: 1; transform: translateY(0); }
.rv.d1 { transition-delay: 0.1s; }
.rv.d2 { transition-delay: 0.2s; }
.rv.d3 { transition-delay: 0.3s; }
.rv.d4 { transition-delay: 0.4s; }
```
- Triggered by IntersectionObserver at `threshold: 0.1`, `rootMargin: '0px 0px -48px 0px'`
- Hero elements are always visible (no `.rv` animation on hero itself)
- Apply `.rv` to every card, stat, and content block
- Apply `.d1`–`.d4` to stagger items in a grid (left to right)

#### Card Hover
```css
/* Lift effect */
.card:hover { transform: translateY(-4px); box-shadow: 0 16px 40px rgba(0,0,0,0.08); }

/* Left accent bar (dark sections — teal) */
.card::before {
  content: '';
  position: absolute;
  left: 0; top: 0;
  width: 3px; height: 0;
  background: #2ddcaa;
  transition: height 0.35s ease;
}
.card:hover::before { height: 100%; }

/* Bottom accent bar (light sections — violet) */
.card::after {
  content: '';
  position: absolute;
  bottom: 0; left: 0; right: 0;
  height: 3px;
  background: transparent;
  transition: background 0.4s;
}
.card:hover::after { background: #6464d7; }

/* Top accent bar (case study cards — teal) */
.card::before {
  height: 2px; width: 100%; background: #2ddcaa; /* always visible */
}
```

#### Global Keyframes
```css
@keyframes hscan {
  0%   { top: -2px; opacity: 0; }
  3%   { opacity: 1; }
  97%  { opacity: 1; }
  100% { top: 100%; opacity: 0; }
}
@keyframes hup {
  from { transform: translateY(22px); opacity: 0; }
  to   { transform: translateY(0); opacity: 1; }
}
@keyframes ticker-scroll {
  from { transform: translateX(0); }
  to   { transform: translateX(-50%); }
}
@keyframes blink {
  0%, 100% { opacity: 1; }
  50%       { opacity: 0.3; }
}
@keyframes fp {
  0%, 100% { transform: scale(1); opacity: 1; }
  50%       { transform: scale(0.7); opacity: 0.5; }
}
@keyframes orbit {
  from { transform: rotate(0deg); }
  to   { transform: rotate(360deg); }
}
```

#### Stat Counter
- On intersect (threshold 0.4), count from 0 to target value
- Duration: 1600ms with cubic ease `1 - (1-p)³`
- Numbers ≥1000 display as `XK`

#### Reduced Motion
```css
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    transition-duration: 0.01ms !important;
  }
}
```

---

### 11. INSIGHTS SECTION LAYOUT RULES

- Background: `#ffffff`
- Section label: `.lbl.lbl--dark` (violet, centered with ruled lines)
- Layout: **horizontal carousel** — 3 cards visible per page, category filters at top, prev/next arrow buttons
- **Every card has a `16:9` dummy image at the top** — no exceptions

**Card structure:**
```html
<article class="in-card">
  <!-- Image — EVERY card has this -->
  <div class="in-img" aria-hidden="true"></div>       <!-- 16:9, CSS gradient dummy -->

  <!-- Body -->
  <div class="in-body">
    <div class="in-type">Whitepaper</div>             <!-- 11px 700 uppercase violet -->
    <h3 class="in-title">[Title]</h3>                 <!-- PP Neue Machina 20px 400 -->
    <p class="in-desc">[Description]</p>              <!-- 14px #333 line-height 1.65 -->
    <a href="#" class="btn btn-text">Read more        <!-- violet text btn -->
      <svg ...arrow/>
    </a>
  </div>
</article>
```

**Card CSS:**
```css
.in-card {
  background: #f4f4f4;
  border: 1px solid #cccccc;
  border-radius: 2px;
  display: flex;
  flex-direction: column;
  overflow: hidden;
  transition: transform 0.25s ease, box-shadow 0.25s ease;
}
.in-card:hover { transform: translateY(-4px); box-shadow: 0 8px 28px rgba(0,0,0,0.07); }
.in-card::after { /* 3px bottom violet bar on hover, position: absolute */ }

.in-img {
  width: 100%;
  aspect-ratio: 16 / 9;
  background: linear-gradient(135deg, #d4d4d4 0%, #f4f4f4 100%); /* light dummy */
  flex-shrink: 0;
}
.in-body { padding: 28px; display: flex; flex-direction: column; flex: 1; }
```

**Filter pills:**
```css
.ins-filter {
  font-size: 13px; font-weight: 600; letter-spacing: 0.08em; text-transform: uppercase;
  padding: 8px 18px; border-radius: 2px;
  border: 1px solid #cccccc; background: transparent; color: #666;
  transition: background 0.15s, color 0.15s, border-color 0.15s;
}
.ins-filter:hover  { border-color: #6464d7; color: #6464d7; }
.ins-filter.active { background: #6464d7; border-color: #6464d7; color: #fff; }
```

**Navigation arrows:** circular, `48px × 48px`, `border: 1px solid #999`, hover fills violet (`#6464d7`)

---

### 12. CASE STUDY SECTION LAYOUT RULES

- Background: `#000000` (dark)
- Section label: `.lbl` (teal)
- Grid: 3 equal columns, no gap (border-divided)

**Card structure — tag is overlaid on the image (bottom-left), NOT below it:**
```html
<article class="cs-card rv">
  <!-- Image with tag overlaid -->
  <div class="cs-img">
    <div class="cs-img-inner"></div>               <!-- CSS gradient dummy -->
    <div class="cs-tag">Healthcare</div>           <!-- tag sits ON image, bottom-left -->
  </div>

  <!-- Card body — no tag here -->
  <div class="cs-body">
    <h3 class="cs-title">[Case Study Title]</h3>  <!-- PP Neue Machina 22px 400 white -->
    <p class="cs-desc">[Description]</p>           <!-- 15px #cccccc line-height 1.65 -->
    <a href="#" class="btn btn-inverse btn-sm">Read case study <svg ...arrow/></a>
  </div>
</article>
```

**Tag CSS — absolute positioned inside image:**
```css
.cs-tag {
  position: absolute;
  bottom: 16px;
  left: 16px;
  font-size: 11px;
  font-weight: 700;
  letter-spacing: 0.12em;
  text-transform: uppercase;
  color: #000;
  background: #2ddcaa;     /* teal pill on the image */
  padding: 4px 10px;
  border-radius: 2px;
  z-index: 2;
}
```

**Card CSS:**
```css
.inc {
  padding: 48px 36px;
  border-right: 1px solid #1a1a1a;
  position: relative;
}
.inc:last-child { border-right: none; }

/* Permanent teal top bar */
.inc::before {
  content: '';
  position: absolute;
  top: 0; left: 0; right: 0;
  height: 2px;
  background: #2ddcaa;
}

/* Image hover: scale + teal bottom bar */
.inc-img { width: 100%; aspect-ratio: 16/9; background: #333; border-radius: 2px; overflow: hidden; }
.inc:hover .inc-img-inner { transform: scale(1.03); }
```

**Dummy image treatment:** `background: linear-gradient(135deg, #333 0%, #1a1a1a 100%)`

---

## STRICT RULES FOR EVERY PAGE

1. **Never invent colors.** Only use the exact hex values and CSS tokens defined above.
2. **Never invent fonts.** Only PP Neue Machina (H1–H3, stats), Inter (H4–H5, body, UI), and Roboto Mono (terminal only).
3. **Never invent spacing.** Use `--px`, `--py`, and the spacing values defined above.
4. **Never invent content.** All copy, headlines, stats, and labels must come from `content.docx`.
5. **Header must always match exactly.** Copy the nav HTML verbatim. Add `.active` to current page's nav link.
6. **Footer must always match exactly.** Copy the footer HTML verbatim. Never modify columns or links.
7. **Labels above headings always follow label style.** Every section heading needs a `.lbl` above it.
8. **Background pattern must alternate** dark/light as specified. Never use two consecutive white sections or two consecutive dark sections.
9. **Dummy images** use CSS gradient placeholders: `background: linear-gradient(135deg, #333 0%, #1a1a1a 100%)` on dark sections, `background: #f4f4f4` on light sections. Always maintain correct aspect ratios.
10. **All cards must have `.rv` class** for scroll reveal. Stagger with `.d1`–`.d4`.
11. **Buttons always include arrow icon.** Use the standard SVG arrow `M3 8h10M9 4l4 4-4 4`.
12. **Border-radius is always `2px`** for cards, buttons, chips, and badges. Never use rounded or circular except for nav control buttons (`48px`).
13. **No shadows on initial state.** Shadows only appear on hover.
14. **Accent bars on cards** are always `3px` height (bottom/top) or `3px` width (left side).
15. **Mobile nav** must include hamburger toggle and drawer. See index.html for reference implementation.
16. **`prefers-reduced-motion`** media query must be included on every page.

# Azuvila Website — Project Context

## About the Site

**azuvila.co** is the marketing website for Azuvila, a woman-owned small business (WOSB) that advises small businesses entering the government contracting market. The site's owner and strategic director is **Maricarmen Smith-Martinez**, founder.

Tagline: *Connecting Purpose with Partners*

The owner provides strategic direction for updates; Claude handles all implementation.

---

## Site Structure

Three plain HTML pages — no framework, no build tool, no npm. Everything is self-contained (inline CSS and JS in each file).

| File | Purpose |
|------|---------|
| `index.html` | Home — hero, approach image, contact form |
| `services.html` | Service offerings — interactive expand/collapse cards |
| `about.html` | About — founder bio, credentials, story |

Supporting assets in root: `logo.png`, `maricarmen.png`, `approach.png`, favicons, `site.webmanifest`, `CNAME`.

---

## Brand & Design Tokens

```css
--navy:      #0a2632   /* primary background, header, service cards */
--light-blue: #7dd3f5  /* accents, CTA buttons, icons, hover states */
--gray-bg:   #f8f9fa   /* alternating section backgrounds */
--text-dark: #333      /* body text */
--text-light: #666     /* secondary/muted text */
```

- **Font:** `'Helvetica Neue', Helvetica, Arial, sans-serif`
- **Max content width:** 1200px (1000px on about.html)
- **Border radius:** 4px (buttons), 8px (cards/containers), 12px (service cards)
- **Responsive breakpoint:** 768px (mobile — single column, hamburger menu)

### CTA Buttons
Always: `background: var(--light-blue)`, `color: var(--navy)`, `font-weight: 600`, `border-radius: 4px`, hover lifts with `translateY(-2px)`.

### Section backgrounds
Alternate between `white` and `var(--gray-bg)`. The contact section on index.html uses `var(--navy)` (dark).

---

## Key Patterns & Conventions

### Navigation
- Sticky header, navy background
- Logo links to `index.html`
- Nav links: Services → `services.html`, About → `about.html`, Contact → `index.html#contact`
- Active page gets `.nav-active` class (light-blue color + 2px bottom border) — set via JS using `location.pathname`
- Mobile: hamburger button (☰), dropdown closes on outside click or nav link click

### Service Cards (services.html)
- Dark navy cards (`background: var(--navy)`) in a 2-column grid
- Click to expand/collapse details via `toggleCard()` — adds `.active` class
- Chevron rotates 180° when expanded
- Detail bullets prefixed with `→` in light-blue
- Current services: Strategic Growth & Business Development, Capture & Proposal Management, Partnership & Teaming Strategy, Organizational Development

### Contact Form (index.html)
- Opens user's default email client via `mailto:` link (no backend)
- Recipient: `maricarmen@azuvila.co`
- Shows inline `.form-success` div after submit (no `alert()`)

### Page Headers (services.html, about.html)
- Navy gradient banner: `linear-gradient(135deg, var(--navy) 0%, #164558 100%)`
- `font-weight: 300` for headline

### CTA Section (services.html, about.html)
- Gray background, centered, links to `index.html#contact`
- Heading: "Ready to grow?", subtext, light-blue button "Get in Touch"

### Footer
- Black background (`#000`), white text, `© 2026 Azuvila. All rights reserved.`

---

## Business Details

- **Legal classification:** Woman-Owned Small Business (WOSB), Small Business
- **NAICS Code:** 541611 — Administrative Management and General Management Consulting Services
- **Contact email:** maricarmen@azuvila.co
- **LinkedIn:** https://www.linkedin.com/company/azuvila/
- **Instagram:** https://www.instagram.com/azuvila.co

---

## Deployment

- **Hosting:** GitHub Pages with custom domain (`azuvila.co`) via `CNAME` file
- **Live branch:** `main` — merging into `main` auto-deploys within ~1 minute
- **Workflow:** develop on a `claude/` feature branch → push → open PR on GitHub → merge to `main`

---

## Compact Instructions

When compacting, always preserve:
- The list of files modified and what changed in each
- Any content decisions (copy, services, structure) made by the user
- The current branch name being worked on

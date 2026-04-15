# Design System: Dixon Painting Co.
Generated: 2026-04-14 | Style: refined-professional | Stack: Astro + Netlify

---

## Color System

### CSS Variables

```css
:root {
  --color-primary: #1E3A5F;
  --color-primary-dark: #152C4A;
  --color-accent: #D97706;
  --color-accent-dark: #B45309;
  --color-neutral-50: #F8FAFC;
  --color-neutral-100: #F1F5F9;
  --color-neutral-200: #E2E8F0;
  --color-neutral-700: #334155;
  --color-neutral-900: #0F172A;
  --color-text: #1E293B;
  --color-text-muted: #64748B;
  --color-bg: #FFFFFF;
  --color-bg-section: #F8FAFC;
}
```

### Color Roles

| Variable | Hex | Usage |
|----------|-----|-------|
| `--color-primary` | #1E3A5F | Navy — header background, section accents, footer (lighter variant), nav |
| `--color-primary-dark` | #152C4A | Hover state on primary elements |
| `--color-accent` | #D97706 | Amber — CTA buttons, phone links, trust signal icons, badge backgrounds |
| `--color-accent-dark` | #B45309 | Hover state on all CTA buttons |
| `--color-neutral-50` | #F8FAFC | Alternating section backgrounds (trust bar, service areas) |
| `--color-neutral-100` | #F1F5F9 | Map placeholder background |
| `--color-neutral-200` | #E2E8F0 | Borders, dividers, card borders |
| `--color-neutral-700` | #334155 | Secondary body text |
| `--color-neutral-900` | #0F172A | Footer background, darkest text |
| `--color-text` | #1E293B | Default body text |
| `--color-text-muted` | #64748B | Captions, micro-copy, placeholder text |
| `--color-bg` | #FFFFFF | Default page background |
| `--color-bg-section` | #F8FAFC | Alternating section background |

### Contrast Check

| Pair | Ratio | WCAG AA |
|------|-------|---------|
| `--color-text` (#1E293B) on `--color-bg` (#FFFFFF) | 14.5:1 | ✓ Pass (AAA) |
| White on `--color-primary` (#1E3A5F) | 8.1:1 | ✓ Pass (AAA) |
| White on `--color-accent` (#D97706) | 3.0:1 | ✓ Pass (large text / UI) — use on buttons only, not body text |
| `--color-text-muted` on `--color-bg` | 5.0:1 | ✓ Pass (AA) |
| White on `--color-neutral-900` (#0F172A) | 17.1:1 | ✓ Pass (AAA) |

> **Note:** Amber (#D97706) on white fails WCAG AA for body text (3.0:1). Use amber exclusively for CTA buttons (white text on amber), interactive links on dark backgrounds, and icons. Never use as body copy color on light backgrounds.

---

## Typography

### Font Stack

```html
<!-- Add to <head> in BaseLayout.astro -->
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700;800&family=Lato:wght@400;600;700&display=swap" rel="stylesheet">
```

```css
:root {
  --font-display: 'Playfair Display', Georgia, serif;
  --font-body: 'Lato', system-ui, sans-serif;
}
```

### Type Scale

| Token | Size | Line Height | Weight | Usage |
|-------|------|-------------|--------|-------|
| h1 | clamp(2.25rem, 5vw, 3.5rem) | 1.1 | 700 | Hero headline |
| h2 | clamp(1.75rem, 3.5vw, 2.5rem) | 1.2 | 700 | Section headings |
| h3 | 1.25rem / 20px | 1.3 | 700 | Card headings, sub-sections |
| body | 1rem / 16px | 1.65 | 400 | Body copy |
| small | 0.875rem / 14px | 1.5 | 400 | Captions, micro-copy |
| label | 0.8rem / 12.8px | 1.5 | 700 | Trust bar labels, badges (uppercase + tracked) |

All h1–h3 use `--font-display` (Playfair Display). Body, small, label use `--font-body` (Lato).

---

## Spacing & Layout

### Spacing Scale (8px grid)

| Token | Value | Usage |
|-------|-------|-------|
| `--space-1` | 8px | Icon padding, tight internal gaps |
| `--space-2` | 16px | Element padding, form gap |
| `--space-3` | 24px | Card padding, component internal padding |
| `--space-4` | 32px | Section sub-divisions |
| `--space-6` | 48px | Component vertical rhythm |
| `--space-8` | 64px | Section padding mobile |
| `--space-12` | 96px | Section padding desktop |

### Container & Breakpoints

```css
:root {
  --container-max: 1280px;
  --container-padding: 1.5rem;
}

.container {
  max-width: var(--container-max);
  margin: 0 auto;
  padding: 0 var(--container-padding);
}

/* Breakpoints */
/* mobile:  < 768px  */
/* tablet:  768px – 1024px */
/* desktop: > 1024px */
/* wide:    > 1280px */
```

---

## Accessibility Requirements

Site-builder must satisfy all items before the PR is opened:

- [ ] All body text: contrast ratio ≥ 4.5:1 against its background
- [ ] Amber (#D97706) used on buttons only (white text on amber) — never on white backgrounds as body text
- [ ] All phone numbers: `<a href="tel:+19166122126">(916) 612-2126</a>` — never plain text
- [ ] All interactive elements: visible `:focus-visible` ring — `outline: 2px solid var(--color-accent); outline-offset: 2px;`
- [ ] Touch targets: minimum 44×44px on mobile (buttons, nav links, form inputs)
- [ ] Images: `alt` attribute on every `<img>` — decorative images use `alt=""`
- [ ] Skip link: `<a href="#main-content" class="sr-only focus:not-sr-only">Skip to content</a>` as first element in `<body>`
- [ ] Forms: every input has explicit `<label for="...">` — placeholder text is supplemental, not a label substitute
- [ ] Heading hierarchy: one `<h1>` per page; `<h2>` for major sections; `<h3>` for sub-sections — no level skipping
- [ ] Mobile sticky CTA bar: `<nav role="navigation" aria-label="Quick contact">`
- [ ] Star ratings in testimonials: `<span aria-label="5 out of 5 stars">★★★★★</span>`
- [ ] Service card icons: `aria-hidden="true"` — service name conveys meaning
- [ ] Map embed: `<iframe title="Dixon Painting Co. service area map">` with `loading="lazy"`
- [ ] Body gets `padding-bottom: 56px` on mobile to prevent content overlap with sticky CTA bar

---

## Component Specifications

### Hero Section

**Layout:** Full-width, `min-height: 85vh` desktop / `100dvh` mobile. Two-column grid: left column (60%) contains headline stack, trust line, dual CTA; right column (40%) contains floating lead capture form card. Mobile: stacked, headline → trust line → CTA button → form below the fold.

**Background:** Real job-site photography (`/images/hero-bg.webp`), full-bleed, with navy overlay `rgba(30,58,95,0.72)`. Preload hero image in `<head>`.

```css
.hero {
  background: linear-gradient(rgba(30,58,95,0.72), rgba(30,58,95,0.72)),
              url('/images/hero-bg.webp') center/cover no-repeat;
  min-height: 85vh;
  display: grid;
  grid-template-columns: 1fr 420px;
  gap: 3rem;
  align-items: center;
  padding: 5rem 1.5rem;
}
@media (max-width: 1024px) {
  .hero { grid-template-columns: 1fr; min-height: 100dvh; }
}
.hero__headline {
  font-family: var(--font-display);
  font-size: clamp(2.25rem, 5vw, 3.5rem);
  font-weight: 700;
  color: #fff;
  line-height: 1.1;
}
.hero__trust-line {
  font-size: 0.875rem;
  color: var(--color-accent);
  font-weight: 600;
  letter-spacing: 0.05em;
  text-transform: uppercase;
  margin: 1rem 0 2rem;
}
.hero__cta-primary {
  background: var(--color-accent);
  color: #fff;
  font-weight: 700;
  padding: 1rem 2rem;
  border-radius: 4px;
  transition: background 0.15s ease;
}
.hero__cta-primary:hover { background: var(--color-accent-dark); }
.hero__form-card {
  background: #fff;
  border-radius: 8px;
  padding: 2rem;
  box-shadow: 0 20px 60px rgba(0,0,0,0.25);
}
```

**Accessibility:** Background image has `role="img" aria-label="Dixon Painting Co. — professional painting in Dixon, CA"`; `<h1>` is the page headline; skip link precedes header.

---

### Sticky Header

**Layout:** Logo left; nav center; phone + CTA button right. Height: 80px desktop → shrinks to 60px on scroll. Background: navy on load → white with bottom border on scroll.

```css
.site-header {
  position: sticky;
  top: 0;
  z-index: 40;
  height: 80px;
  background: var(--color-primary);
  transition: height 0.2s ease, background 0.2s ease, box-shadow 0.2s ease;
  display: flex;
  align-items: center;
}
.site-header.scrolled {
  height: 60px;
  background: #fff;
  box-shadow: 0 1px 0 var(--color-neutral-200);
}
.site-header__phone {
  color: var(--color-accent);
  font-weight: 700;
  font-size: 1rem;
  transition: color 0.2s;
}
.site-header.scrolled .site-header__phone { color: var(--color-primary); }
.site-header__cta {
  background: var(--color-accent);
  color: #fff;
  padding: 0.6rem 1.25rem;
  border-radius: 4px;
  font-weight: 700;
  font-size: 0.875rem;
  margin-left: 1rem;
  transition: background 0.15s ease;
}
.site-header__cta:hover { background: var(--color-accent-dark); }
```

**Scroll behavior:** `IntersectionObserver` on a sentinel element; adds `.scrolled` class when viewport scrolls past sentinel.

**Mobile:** Logo left, hamburger right, 60px height. Phone number hidden in header (appears in mobile sticky bar).

**Accessibility:** `<header role="banner">`; logo `<img alt="Dixon Painting Co.">`.

---

### Lead Capture Form

**Fields:** Full Name (text) → Phone Number (tel) → Email (email, optional) → Service Needed (select: Interior Painting / Exterior Painting / Cabinet Painting / Commercial / Not Sure) → Submit button.

```css
.lead-form__label {
  display: block;
  font-size: 0.875rem;
  font-weight: 600;
  color: var(--color-text);
  margin-bottom: 0.25rem;
}
.lead-form__input,
.lead-form__select {
  width: 100%;
  height: 48px;
  padding: 0 1rem;
  border: 1.5px solid var(--color-neutral-200);
  border-radius: 4px;
  font-family: var(--font-body);
  font-size: 1rem;
  color: var(--color-text);
  transition: border-color 0.15s ease, box-shadow 0.15s ease;
}
.lead-form__input:focus,
.lead-form__select:focus {
  border-color: var(--color-accent);
  outline: none;
  box-shadow: 0 0 0 3px rgba(217,119,6,0.15);
}
.lead-form__button {
  width: 100%;
  height: 52px;
  background: var(--color-accent);
  color: #fff;
  font-weight: 700;
  font-size: 1rem;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  transition: background 0.15s ease;
  margin-top: 0.75rem;
}
.lead-form__button:hover { background: var(--color-accent-dark); }
.lead-form__trust {
  font-size: 0.8rem;
  color: var(--color-text-muted);
  text-align: center;
  margin-top: 0.75rem;
}
/* Trust micro-copy: "We respond within 24 hours. No spam, ever." */
```

**Phone field:** `type="tel" inputmode="numeric" autocomplete="tel"`. **Accessibility:** Explicit `<label for="...">` on all inputs; `aria-required="true"` on required fields; errors use `aria-describedby`.

---

### Offer Band

**Full-width section, navy background, centered content. Urgency badge → headline → sub-copy → dual CTA (primary + phone outline).**

```css
.offer-band {
  background: var(--color-primary);
  padding: 5rem 1.5rem;
  text-align: center;
}
.offer-band__badge {
  display: inline-block;
  background: var(--color-accent);
  color: #fff;
  font-size: 0.75rem;
  font-weight: 700;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  padding: 0.35rem 1rem;
  border-radius: 2px;
  margin-bottom: 1.25rem;
}
.offer-band__headline {
  font-family: var(--font-display);
  font-size: clamp(1.75rem, 4vw, 2.5rem);
  font-weight: 700;
  color: #fff;
  margin-bottom: 0.75rem;
}
.offer-band__sub { color: rgba(255,255,255,0.8); font-size: 1.05rem; margin-bottom: 2rem; }
.offer-band__cta-primary {
  background: var(--color-accent);
  color: #fff;
  padding: 1rem 2.25rem;
  border-radius: 4px;
  font-weight: 700;
  transition: background 0.15s;
}
.offer-band__cta-primary:hover { background: var(--color-accent-dark); }
.offer-band__cta-phone {
  border: 2px solid rgba(255,255,255,0.5);
  color: #fff;
  padding: 1rem 2.25rem;
  border-radius: 4px;
  font-weight: 600;
  transition: border-color 0.15s;
}
.offer-band__cta-phone:hover { border-color: #fff; }
```

**Placement:** Between Services section and Testimonials on homepage.

---

### Services Grid

**Layout:** `auto-fit, minmax(240px, 1fr)` — 1 col mobile / 2 col tablet / 4 col desktop (for 4 services). Each card: icon → service name → benefit sentence → "Learn about [Service] →" link.

```css
.services-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(240px, 1fr)); gap: 1.5rem; }
.service-card {
  background: #fff;
  border: 1px solid var(--color-neutral-200);
  border-radius: 8px;
  padding: 2rem 1.5rem;
  transition: box-shadow 0.15s ease, transform 0.15s ease;
}
.service-card:hover {
  box-shadow: 0 8px 24px rgba(30,58,95,0.1);
  transform: translateY(-2px);
}
.service-card__icon { width: 44px; height: 44px; color: var(--color-accent); margin-bottom: 1rem; }
.service-card__name {
  font-family: var(--font-display);
  font-size: 1.125rem;
  font-weight: 700;
  color: var(--color-primary);
  margin-bottom: 0.5rem;
}
.service-card__benefit { font-size: 0.9rem; color: var(--color-text-muted); line-height: 1.6; margin-bottom: 1rem; }
.service-card__link { font-size: 0.875rem; font-weight: 600; color: var(--color-accent); }
.service-card__link:hover { text-decoration: underline; }
```

**Icon:** SVG from Heroicons or Lucide. `aria-hidden="true"`. Link text: "Learn about Interior Painting" (not "Learn More").

---

### Trust Signals Bar

**Full-width horizontal bar on `--color-neutral-50`, 5 badges in a row (wraps on mobile). Each badge: amber SVG icon + bold text.**

```css
.trust-bar {
  background: var(--color-neutral-50);
  border-top: 1px solid var(--color-neutral-200);
  border-bottom: 1px solid var(--color-neutral-200);
  padding: 1.5rem;
}
.trust-bar__list { display: flex; flex-wrap: wrap; justify-content: center; gap: 2rem 3rem; list-style: none; }
.trust-bar__item { display: flex; align-items: center; gap: 0.6rem; font-size: 0.875rem; font-weight: 600; color: var(--color-neutral-900); }
.trust-bar__icon { width: 20px; height: 20px; color: var(--color-accent); flex-shrink: 0; }
```

**Content:** Licensed & Insured | Locally Owned — Dixon, CA | Free Color Consultation | Serving Dixon + 20 Miles | Free Estimates — No Pressure

Icons: `aria-hidden="true"` — text alone conveys the signal.

---

### Testimonials Section

**White section background (alternates from neutral-50). 3-column desktop / 1-column mobile. Each card: stars → quote (italic) → avatar + name + city.**

```css
.testimonials { padding: 5rem 1.5rem; background: #fff; }
.testimonials__grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 1.5rem; margin-top: 3rem; }
.testimonial-card {
  background: #fff;
  border: 1px solid var(--color-neutral-200);
  border-radius: 8px;
  padding: 1.75rem;
  box-shadow: 0 2px 12px rgba(0,0,0,0.05);
}
.testimonial-card__stars { color: var(--color-accent); font-size: 1rem; letter-spacing: 0.1em; margin-bottom: 0.75rem; }
.testimonial-card__quote { font-size: 0.975rem; line-height: 1.7; color: var(--color-neutral-700); font-style: italic; margin-bottom: 1.25rem; }
.testimonial-card__reviewer { display: flex; align-items: center; gap: 0.75rem; }
.testimonial-card__avatar { width: 44px; height: 44px; border-radius: 50%; object-fit: cover; }
.testimonial-card__name { font-weight: 600; font-size: 0.875rem; color: var(--color-neutral-900); }
.testimonial-card__city { font-size: 0.8rem; color: var(--color-text-muted); }
```

**Accessibility:** Stars: `<span aria-label="5 out of 5 stars">★★★★★</span>`. Avatar: `alt="[Name]"`.

---

### Service Area Section

**Two-column layout desktop: left = heading + intro + city list grid / right = map embed placeholder. Background: `--color-neutral-50`.**

```css
.service-areas { padding: 5rem 1.5rem; background: var(--color-neutral-50); }
.service-areas__layout { display: grid; grid-template-columns: 1fr 1fr; gap: 3rem; align-items: start; }
@media (max-width: 768px) { .service-areas__layout { grid-template-columns: 1fr; } }
.service-areas__city-list {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 0.5rem 1.5rem;
  list-style: none;
  margin-top: 1.5rem;
}
.service-areas__city-list a { color: var(--color-primary); font-weight: 500; font-size: 0.975rem; text-decoration: none; }
.service-areas__city-list a:hover { color: var(--color-accent); }
.service-areas__map { aspect-ratio: 4/3; background: var(--color-neutral-200); border-radius: 8px; overflow: hidden; }
.service-areas__map iframe { width: 100%; height: 100%; border: none; }
```

Map embed: `loading="lazy"` + `title="Dixon Painting Co. service area map"`.

---

### Footer

**Background: `#0F172A` (darker navy). 4-column desktop / 2-column tablet / stacked mobile. Columns: (1) Logo + tagline + NAP block / (2) Services / (3) Service Areas / (4) Company links.**

```css
.site-footer { background: #0F172A; color: rgba(255,255,255,0.75); padding: 4rem 1.5rem 2rem; }
.site-footer__grid { display: grid; grid-template-columns: 2fr 1fr 1fr 1fr; gap: 3rem; margin-bottom: 3rem; }
@media (max-width: 1024px) { .site-footer__grid { grid-template-columns: 1fr 1fr; } }
@media (max-width: 640px) { .site-footer__grid { grid-template-columns: 1fr; } }
.site-footer__heading { font-size: 0.75rem; font-weight: 700; letter-spacing: 0.1em; text-transform: uppercase; color: var(--color-accent); margin-bottom: 1rem; }
.site-footer__link { display: block; font-size: 0.875rem; color: rgba(255,255,255,0.65); margin-bottom: 0.5rem; text-decoration: none; transition: color 0.15s; }
.site-footer__link:hover { color: #fff; }
.site-footer__phone-link { color: var(--color-accent); font-weight: 700; font-size: 1rem; }
.site-footer__bottom { font-size: 0.8rem; color: rgba(255,255,255,0.4); border-top: 1px solid rgba(255,255,255,0.1); padding-top: 1.5rem; }
```

**Accessibility:** `<footer role="contentinfo">`; phone wrapped in `<a href="tel:+19166122126">`.

---

### Mobile Sticky CTA Bar

**Fixed bottom, mobile only (`max-width: 767px`). Two equal columns: left = phone tap-to-call / right = Get Estimate button. Height 56px, z-index 50.**

```css
.mobile-cta-bar {
  position: fixed;
  bottom: 0;
  left: 0;
  right: 0;
  height: 56px;
  z-index: 50;
  background: var(--color-primary);
  display: grid;
  grid-template-columns: 1fr 1fr;
  border-top: 1px solid rgba(255,255,255,0.1);
}
@media (min-width: 768px) { .mobile-cta-bar { display: none; } }
.mobile-cta-bar__call {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 0.4rem;
  color: #fff;
  font-weight: 600;
  font-size: 0.9rem;
  text-decoration: none;
  border-right: 1px solid rgba(255,255,255,0.15);
}
.mobile-cta-bar__quote {
  display: flex;
  align-items: center;
  justify-content: center;
  background: var(--color-accent);
  color: #fff;
  font-weight: 700;
  font-size: 0.9rem;
  text-decoration: none;
}
.mobile-cta-bar__quote:active { background: var(--color-accent-dark); }
```

Body padding on mobile:
```css
@media (max-width: 767px) { body { padding-bottom: 56px; } }
```

**Accessibility:** `<nav role="navigation" aria-label="Quick contact">`; both links have descriptive `aria-label` (e.g., `aria-label="Call Dixon Painting Co. at (916) 612-2126"`).

---

## Aesthetic Brief for site-builder

Dixon Painting Co. presents itself as the skilled local craftsman your neighbors trust — not a franchise website, not a corporate contractor chain. The design expresses this through restraint and precision: deep navy authority, warm amber action, clean serif headlines that suggest quality without pretension.

Every section has a clear job. The hero lands the value proposition above the fold and immediately presents the lead form — no scrolling required to make contact. The trust signals bar appears early and without fanfare: it's not a boast, it's a reassurance. The gallery carries the weight of the pitch — real before/after photography of real Dixon-area homes does more work than any headline. The footer doubles down on the NAP block and phone number because mobile users often scroll to the bottom specifically to call.

Motion is minimal and purposeful. The sticky header shrinks on scroll using a CSS transition (not JS-driven janky layout shifts). Service cards lift 2px on hover with a box-shadow reveal — a subtle cue that they're clickable. Nothing animates on its own; nothing blinks, pulses, or draws attention away from the estimate form. The one exception is the mobile sticky CTA bar, which fades in after the page loads (CSS `@keyframes` fade, 300ms, `animation-delay: 500ms`) — giving the user a moment to orient before the bar appears. The overall feel: local, professional, and completely focused on getting that phone to ring.

---

## Image Brief

> Consumed by site-builder Agent 7 (Image Planner) to produce the image manifest.
> Prompts written for Nano Banana (photorealistic). Pexels queries are fallback search terms.

### Hero Background
- **Filename:** `hero-bg`
- **Dimensions:** 1920×1080
- **Prompt:** "professional painter rolling exterior wall of suburban California home, golden hour light, crisp clean lines, no faces, cinematic shallow depth of field"
- **Pexels query:** "house painter exterior professional California"
- **Alt text:** "Dixon Painting Co. — professional painting contractor in Dixon, CA"
- **Usage:** Hero section full-width background; navy overlay `rgba(30,58,95,0.72)` applied in CSS

### Service Images

- **Filename:** `service-interior-painting`
- **Dimensions:** 800×600
- **Prompt:** "professional interior room freshly painted white walls, clean lines, painter's tape removed, warm natural light through windows"
- **Pexels query:** "interior painting fresh white walls professional"
- **Alt text:** "Interior painting by Dixon Painting Co."
- **Usage:** Interior Painting service card and page hero

- **Filename:** `service-exterior-painting`
- **Dimensions:** 800×600
- **Prompt:** "freshly painted suburban home exterior, crisp trim, ladder and equipment visible in background, blue sky California"
- **Pexels query:** "exterior house painting professional California"
- **Alt text:** "Exterior painting by Dixon Painting Co."
- **Usage:** Exterior Painting service card and page hero

- **Filename:** `service-cabinet-painting`
- **Dimensions:** 800×600
- **Prompt:** "kitchen cabinet painting transformation, freshly painted white cabinets, clean finish, modern kitchen California home"
- **Pexels query:** "kitchen cabinet painting professional white"
- **Alt text:** "Cabinet painting by Dixon Painting Co."
- **Usage:** Cabinet Painting service card and page hero

- **Filename:** `service-commercial-painting`
- **Dimensions:** 800×600
- **Prompt:** "commercial office space interior freshly painted, clean white walls, professional environment, bright lighting"
- **Pexels query:** "commercial painting office interior professional"
- **Alt text:** "Commercial painting by Dixon Painting Co."
- **Usage:** Commercial Painting service card and page hero

### About / Team
- **Filename:** `about-team`
- **Dimensions:** 800×600
- **Prompt:** "local painting contractor standing in front of freshly painted home exterior, professional work clothes, confident and approachable, California suburban"
- **Pexels query:** "painting contractor professional team workwear"
- **Alt text:** "The Dixon Painting Co. team"
- **Usage:** About page hero section

### Gallery Before/After Pairs
- **Filename:** `gallery-before-{N}` / `gallery-after-{N}` (N = 1–4)
- **Dimensions:** 800×600 each
- **Prompt before:** "room or home exterior before painting — faded paint, dated color, worn surfaces"
- **Prompt after:** "same space after professional painting — fresh color, clean lines, transformed look"
- **Pexels query:** "before after room painting transformation"
- **Alt text:** "Before: [description] — After: Fresh paint by Dixon Painting Co."

### Testimonial Avatars
- **Filenames:** `testimonial-avatar-1`, `testimonial-avatar-2`, `testimonial-avatar-3`
- **Dimensions:** 200×200
- **Prompt:** "professional portrait, diverse, smiling, natural light, neutral background — no text, no logo"
- **Pexels query:** "professional portrait smiling person natural light"
- **Alt text:** `alt=""` (decorative — reviewer name in text below)
- **Note:** No responsive variants — single 200×200 WebP only

### OG / Social Sharing Image
- **Filename:** `og-image`
- **Dimensions:** 1200×630
- **Derived from:** `hero-bg` — resized/cropped to 1200×630, no separate API call
- **Alt text:** "Dixon Painting Co. — painting contractor in Dixon, CA"
- **Usage:** `og:image` meta tag on all pages
- **Note:** Agent 7 produces this automatically from hero-bg after download (crop + resize). No separate manifest entry needed.

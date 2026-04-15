# Build Plan: Dixon Painting Co.
Generated: 2026-04-14 | Stack: Astro SSG | Deploy: Netlify | Auth: None

---

## Stack Scout Output

**Scaffold command:**
```
npm create astro@latest . -- --template minimal --no-install --no-git --skip-houston
```

**Dependencies:**
- `@astrojs/tailwind`, `@astrojs/sitemap`, `tailwindcss`, `@tailwindcss/typography`

**Dev dependencies:**
- `prettier`, `prettier-plugin-astro`

**Config files:** astro.config.mjs, tailwind.config.mjs, src/styles/global.css, netlify.toml

**17 pages:** /, /services, /services/interior-painting, /services/exterior-painting, /services/cabinet-painting, /services/commercial-painting, /gallery, /service-areas, /service-areas/vacaville, /service-areas/woodland, /service-areas/fairfield, /service-areas/davis, /about, /blog, /contact, /privacy, /terms

---

## Component Analyst Output

**10 components:**
1. `src/layouts/BaseLayout.astro` — props: title, description, ogImage, canonicalUrl
2. `src/components/Header.astro` — props: currentPath; sticky nav, scroll shrink via IntersectionObserver
3. `src/components/Footer.astro` — 4-col grid, NAP block, all links
4. `src/components/MobileStickyCTABar.astro` — fixed bottom, 56px, fade-in 500ms
5. `src/components/LeadCaptureForm.astro` — Netlify Forms, honeypot, JS fetch submit
6. `src/components/Hero.astro` — props: headline, subheadline, showForm
7. `src/components/ServicesGrid.astro` — 4 service cards, auto-fit grid
8. `src/components/TrustSignalsBar.astro` — 5 badges, horizontal flex
9. `src/components/TestimonialsSection.astro` — 3 cards, stars aria-label
10. `src/components/OfferBand.astro` — navy band, urgency badge, dual CTA

---

## SEO Mapper Output

**SEO data file:** `docs/seo-map.json` (17 pages with title, desc, OG, canonical, breadcrumbs, sitemap priority)

**LocalBusiness JSON-LD:** HomeAndConstructionBusiness, Dixon CA, 5 cities in areaServed, M-F 8-6 / Sat 9-2

**Sitemap:** all 17 pages, lastmod 2026-04-14

**robots.txt:** Allow all, Sitemap: https://dixonpaintingco.com/sitemap.xml

---

## Copy Integrator Output

**Copy file:** `docs/copy.json` (14 page copy objects with all hero, sections, CTAs)

All copy sourced from site-plan.md copy brief. No placeholder text used.

---

## Conversion Optimizer Output

**Conversion spec:** `docs/conversion-spec.json`

**Homepage section order:** Hero → TrustSignalsBar → ServicesGrid → OfferBand → TestimonialsSection → ServiceAreaSection → FAQSection → FinalCTABand

**Form placements:** hero right column (desktop), below hero mobile, final-cta-band, /contact

**Vanilla JS:** formSubmit, headerScroll (IntersectionObserver), mobileMenu, faqAccordion

**Netlify Forms:** data-netlify="true", honeypot, hidden form-name field

---

## Image Planner Output

**Image manifest:** `.web-studio/image-manifest.json` (18 entries: 17 to generate + 1 derived)

API: Nano Banana (NANOBANANA_API_KEY found) with Pexels fallback

Priority: hero-bg → service images → about-team → gallery pairs → testimonial avatars → og-image

---

## Build Phase Checklist

- [x] Phase R: Research complete (6 agents)
- [ ] Phase B1: Scaffold + config files
- [ ] Phase B1.5: Image generation
- [ ] Phase B2: Shared components
- [ ] Phase B3: Homepage
- [ ] Phase B4: Inner pages
- [ ] Phase B5: SEO layer
- [ ] Phase B7: Deploy prep + build verify
- [ ] PR creation

---

## Phone Number Rule

Every instance: `<a href="tel:+19166122126">(916) 612-2126</a>` — never plain text.

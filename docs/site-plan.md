# Site Plan: Dixon Painting Co.
Generated: 2026-04-14 | Site Type: Service (Painting) | Stack: Astro + Netlify

---

## Site Architecture

### Page Hierarchy (ASCII Tree)

```
Homepage (/)
├── Services (/services)
│   ├── Interior Painting (/services/interior-painting)
│   ├── Exterior Painting (/services/exterior-painting)
│   ├── Cabinet Painting (/services/cabinet-painting)
│   └── Commercial Painting (/services/commercial-painting)
├── Gallery (/gallery)
├── Service Areas (/service-areas)
│   ├── Vacaville (/service-areas/vacaville)
│   ├── Woodland (/service-areas/woodland)
│   ├── Fairfield (/service-areas/fairfield)
│   └── Davis (/service-areas/davis)
├── About (/about)
├── Blog (/blog)
│   └── [Post slug] (/blog/[slug])
└── Contact (/contact)
```

### Navigation Spec

**Header Nav** (left to right):
1. Services *(dropdown: Interior Painting, Exterior Painting, Cabinet Painting, Commercial Painting)*
2. Gallery
3. Service Areas
4. About
5. Blog
6. **Get Free Estimate** *(CTA button — rightmost, accent color)*

- Logo (left) links to `/`
- Phone number displayed in top bar above nav: `(916) 612-2126` — tap-to-call on mobile
- Sticky header on scroll — phone + CTA always visible
- Mobile: hamburger menu + sticky bottom bar with `📞 Call Now` + `Get Estimate` buttons

**Footer Sections:**

| Column 1 — Services | Column 2 — Areas | Column 3 — Company | Column 4 — Legal |
|---------------------|------------------|--------------------|------------------|
| Interior Painting | Vacaville | About | Privacy Policy |
| Exterior Painting | Woodland | Blog | Terms |
| Cabinet Painting | Fairfield | Contact | |
| Commercial Painting | Davis | | |

Footer also includes: NAP block, Licensed & Insured badge, Google Reviews link.

**Breadcrumbs:**
- Service subpages: `Home > Services > Interior Painting`
- City pages: `Home > Service Areas > Vacaville`
- Blog posts: `Home > Blog > [Post Title]`

### Internal Linking Plan

**Hub pages and spokes:**

| Hub | Spokes |
|-----|--------|
| `/services` | All 4 service subpages; linked from homepage services section, footer |
| `/service-areas` | All 4 city pages; linked from homepage footer CTA band, contact page |
| `/blog` | Individual posts; each post links back to the relevant service page |

**Cross-section links:**

| From | To | Anchor Text | Placement |
|------|----|-------------|-----------|
| `/services/interior-painting` | `/contact` | "Get a Free Interior Painting Estimate" | Body CTA |
| `/services/exterior-painting` | `/gallery` | "See Our Exterior Work" | Body |
| `/gallery` | `/contact` | "Ready to Transform Your Home?" | Page bottom CTA |
| `/service-areas/[city]` | `/services` | "View Our Full Painting Services" | Body |
| `/service-areas/[city]` | `/contact` | "Get a Free Estimate in [City]" | Hero CTA |
| `/about` | `/contact` | "Request a Free Estimate" | Page bottom CTA |
| `/blog/[slug]` | Relevant service page | Contextual anchor | Body |
| Homepage | `/gallery` | "See Our Work" | Services section |
| Homepage | `/service-areas` | "We Serve Dixon + 20 Miles" | Footer band |

---

## Page Inventory

| Page | URL | Priority | Notes |
|------|-----|----------|-------|
| Homepage | `/` | P1 | Primary conversion page |
| Services | `/services` | P1 | Services index |
| Interior Painting | `/services/interior-painting` | P1 | High search volume service |
| Exterior Painting | `/services/exterior-painting` | P1 | High search volume service |
| Cabinet Painting | `/services/cabinet-painting` | P2 | Growing demand, high value |
| Commercial Painting | `/services/commercial-painting` | P2 | B2B lead gen |
| Gallery | `/gallery` | P1 | Trust-builder, conversion support |
| Service Areas | `/service-areas` | P1 | Local SEO hub |
| Vacaville | `/service-areas/vacaville` | P2 | Local SEO city page |
| Woodland | `/service-areas/woodland` | P2 | Local SEO city page |
| Fairfield | `/service-areas/fairfield` | P2 | Local SEO city page |
| Davis | `/service-areas/davis` | P2 | Local SEO city page |
| About | `/about` | P2 | Trust and credibility |
| Blog | `/blog` | P3 | SEO content hub |
| Blog Post | `/blog/[slug]` | P3 | Long-tail keyword content |
| Contact | `/contact` | P1 | Lead capture form + phone |
| Privacy Policy | `/privacy` | P4 | Legal requirement |
| Terms | `/terms` | P4 | Legal requirement |

---

## SEO Strategy

### Primary Keyword
`painting contractor Dixon CA`

### Secondary Keywords

| Pattern | Keyword |
|---------|---------|
| Trade + City | `painter Dixon CA` |
| Service + City | `interior painting Dixon CA` |
| Service + City | `exterior painting Dixon CA` |
| Service + City | `cabinet painting Dixon CA` |
| Service + City | `commercial painting Dixon CA` |
| Near-me | `painting contractor near me` |
| Near-me | `house painter near me` |
| Near-me | `interior painter near me` |
| Trade + Vacaville | `painter Vacaville CA` |
| Trade + Woodland | `painting contractor Woodland CA` |
| Trade + Fairfield | `painter Fairfield CA` |
| Trade + Davis | `painting contractor Davis CA` |
| Trust | `licensed painting contractor Dixon` |
| Trust | `residential painter Dixon CA` |

### Long-tail Blog Keywords
- `how much does interior painting cost in Dixon CA`
- `best paint colors for home exterior California`
- `how to choose paint colors for your home`
- `cabinet painting vs replacing cabinets cost`
- `how to prepare walls before painting`
- `how long does exterior house paint last`

---

## Keyword Map

| Page | Primary Keyword | Secondary Keywords | Title Tag | Meta Description |
|------|----------------|-------------------|-----------|-----------------|
| `/` | `painting contractor Dixon CA` | `painter Dixon CA`, `house painter near me` | `Painting Contractor in Dixon, CA \| Dixon Painting Co.` | `Dixon Painting Co. offers professional interior & exterior painting in Dixon, CA and surrounding areas. Free estimates. Call (916) 612-2126.` |
| `/services` | `painting services Dixon CA` | `painting company Dixon`, `painter Dixon CA` | `Painting Services in Dixon, CA \| Dixon Painting Co.` | `From interior to exterior and cabinet painting, Dixon Painting Co. delivers quality results for homeowners & businesses. Get your free estimate today.` |
| `/services/interior-painting` | `interior painting Dixon CA` | `interior painter near me`, `house painter Dixon` | `Interior Painting in Dixon, CA \| Dixon Painting Co.` | `Professional interior painting services in Dixon, CA. Clean, precise, and on schedule. Call (916) 612-2126 for a free estimate from Dixon Painting Co.` |
| `/services/exterior-painting` | `exterior painting Dixon CA` | `exterior house painter Dixon`, `house painting near me` | `Exterior Painting in Dixon, CA \| Dixon Painting Co.` | `Protect and beautify your home with expert exterior painting in Dixon, CA. Weather-resistant finishes, free estimates. Dixon Painting Co. — (916) 612-2126.` |
| `/services/cabinet-painting` | `cabinet painting Dixon CA` | `kitchen cabinet painting near me`, `cabinet refinishing Dixon` | `Cabinet Painting in Dixon, CA \| Dixon Painting Co.` | `Refresh your kitchen with professional cabinet painting in Dixon, CA. Fraction of replacement cost. Call Dixon Painting Co. at (916) 612-2126 for a free quote.` |
| `/services/commercial-painting` | `commercial painting contractor Dixon CA` | `commercial painter near me`, `office painting Dixon` | `Commercial Painting Contractor Dixon, CA \| Dixon Painting Co.` | `Reliable commercial painting services for businesses in Dixon, CA and nearby areas. Minimal disruption, quality results. Call (916) 612-2126.` |
| `/gallery` | `painting contractor portfolio Dixon CA` | `before after painting Dixon`, `painting examples Dixon` | `Our Work \| Dixon Painting Co. — Painting Contractor Dixon, CA` | `Browse before & after photos of interior, exterior, and cabinet painting projects completed by Dixon Painting Co. in Dixon, CA and surrounding areas.` |
| `/service-areas` | `painting contractor near Dixon CA` | `painter near me`, `painting company near Dixon` | `Service Areas \| Dixon Painting Co. — Dixon, Vacaville, Woodland & More` | `Dixon Painting Co. serves Dixon, Vacaville, Woodland, Fairfield, Davis, and all cities within 20 miles. Call (916) 612-2126 for a free estimate.` |
| `/service-areas/vacaville` | `painter Vacaville CA` | `painting contractor Vacaville`, `house painter Vacaville` | `Painting Contractor in Vacaville, CA \| Dixon Painting Co.` | `Dixon Painting Co. provides interior & exterior painting services in Vacaville, CA. Licensed, insured, and locally trusted. Free estimates — (916) 612-2126.` |
| `/service-areas/woodland` | `painting contractor Woodland CA` | `painter Woodland CA`, `house painter Woodland` | `Painting Contractor in Woodland, CA \| Dixon Painting Co.` | `Professional painting services in Woodland, CA from Dixon Painting Co. Residential & commercial. Free estimates available. Call (916) 612-2126.` |
| `/service-areas/fairfield` | `painter Fairfield CA` | `painting contractor Fairfield`, `exterior painter Fairfield` | `Painting Contractor in Fairfield, CA \| Dixon Painting Co.` | `Serving Fairfield, CA with quality interior and exterior painting. Dixon Painting Co. — licensed, insured, and local. Call (916) 612-2126.` |
| `/service-areas/davis` | `painting contractor Davis CA` | `painter Davis CA`, `house painter Davis` | `Painting Contractor in Davis, CA \| Dixon Painting Co.` | `Interior, exterior, and cabinet painting in Davis, CA. Dixon Painting Co. serves the Davis area with free estimates and professional results. (916) 612-2126.` |
| `/about` | `painting contractor Dixon CA` | `local painter Dixon`, `Dixon painting company` | `About Dixon Painting Co. \| Local Painters in Dixon, CA` | `Learn about Dixon Painting Co. — a locally trusted painting contractor serving Dixon, CA and surrounding communities. Licensed, insured, and committed to quality.` |
| `/blog` | `painting tips Dixon CA` | `painting advice`, `home painting ideas` | `Painting Tips & Resources \| Dixon Painting Co. Blog` | `Expert painting tips, color inspiration, and home improvement advice from Dixon Painting Co. — your local painting contractor in Dixon, CA.` |
| `/contact` | `free painting estimate Dixon CA` | `painting estimate near me`, `free quote painter Dixon` | `Contact Us \| Free Painting Estimate — Dixon Painting Co.` | `Get your free painting estimate from Dixon Painting Co. in Dixon, CA. Call (916) 612-2126 or fill out our online form. We serve Dixon + 20 miles.` |

---

## Schema Markup Spec

```json
{
  "@context": "https://schema.org",
  "@type": "HomeAndConstructionBusiness",
  "name": "Dixon Painting Co.",
  "url": "[site URL — TBD until deployed]",
  "telephone": "+19166122126",
  "address": {
    "@type": "PostalAddress",
    "streetAddress": "[REQUIRED — supply before launch]",
    "addressLocality": "Dixon",
    "addressRegion": "CA",
    "postalCode": "[REQUIRED — supply before launch]",
    "addressCountry": "US"
  },
  "areaServed": [
    { "@type": "City", "name": "Dixon" },
    { "@type": "City", "name": "Vacaville" },
    { "@type": "City", "name": "Woodland" },
    { "@type": "City", "name": "Fairfield" },
    { "@type": "City", "name": "Davis" }
  ],
  "openingHoursSpecification": [
    {
      "@type": "OpeningHoursSpecification",
      "dayOfWeek": ["Monday","Tuesday","Wednesday","Thursday","Friday"],
      "opens": "08:00",
      "closes": "18:00"
    },
    {
      "@type": "OpeningHoursSpecification",
      "dayOfWeek": ["Saturday"],
      "opens": "09:00",
      "closes": "14:00"
    }
  ],
  "priceRange": "$$",
  "sameAs": [
    "[Google Business Profile URL — TBD]",
    "[Facebook URL — TBD]",
    "[Yelp URL — TBD]"
  ]
}
```

> **⚠️ Required before launch:** `streetAddress`, `postalCode`, and all `sameAs` URLs must be filled in. Leaving these blank breaks NAP consistency with Google Business Profile and directory listings.

---

## Performance Targets (Astro + Netlify)

| Metric | Target | Notes |
|--------|--------|-------|
| LCP | < 2.5s | Preload hero image; use `<Image>` from `astro:assets` |
| CLS | < 0.1 | Declare width/height on all images |
| INP | < 200ms | Minimize JS islands; `client:idle` or `client:visible` only |
| TTFB | < 600ms | Full SSG; Netlify CDN handles distribution |
| Image format | WebP/AVIF | Astro handles conversion automatically |

**Astro-specific:**
- All pages generated as static HTML at build time (SSG)
- Use `@astrojs/sitemap` — submit `sitemap.xml` to Google Search Console at launch
- `client:*` directives limited to lead capture form only
- Use `<ViewTransitions />` for smooth navigation

### NAP Consistency Requirements

Use this exact format everywhere — header, footer, contact page, schema, Google Business Profile, Yelp, Angi, HomeAdvisor:

- **Name:** Dixon Painting Co.
- **Phone:** (916) 612-2126
- **City/State:** Dixon, CA

---

## Copy Brief

### Homepage Copy

**Headline:** Your Home Deserves a Fresh Start — We Make It Happen
**Headline Alt A:** Dixon's Trusted Painters — Clean Work, Beautiful Results
**Headline Alt B:** From Dull to Done Right — Professional Painting in Dixon, CA

**Subheadline:** Dixon Painting Co. handles interior, exterior, and cabinet painting for homeowners and businesses across Dixon and the surrounding area. Free color consultations. No pressure estimates.

**Hero Body:** You don't need a paint project to turn into a headache. We show up on time, protect your space, and leave it cleaner than we found it. Whether you're refreshing a single room or repainting the whole exterior, Dixon Painting Co. delivers a finish that lasts — and a process that doesn't stress you out.

**Primary CTA:** Get My Free Estimate
**Urgency CTA:** Call Now — (916) 612-2126

**Services Section Intro:** From walls to cabinets to commercial spaces, we handle the full range of painting work that homeowners and business owners in Dixon and beyond need done right.

**Trust Signals:**
- Licensed & Insured — Full coverage on every job
- Locally Owned — Based right here in Dixon, CA
- Clean, Punctual, Reliable — We respect your home and your schedule
- Free Color Consultation — We help you choose before you commit
- Serving Dixon + 20 Miles — Including Vacaville, Woodland, Fairfield & Davis

**FAQ:**
- Q: Do I need to move my furniture before you arrive? / A: We handle all furniture moving and protection as part of our prep work — you don't need to do anything.
- Q: How long does an interior painting job take? / A: Most single-room jobs take one day. Full interior projects typically run 2–4 days depending on home size and scope.
- Q: What brands of paint do you use? / A: We use professional-grade paints (Sherwin-Williams and Benjamin Moore by default) unless you have a preference — we're happy to work with your choice.
- Q: Do you offer free estimates? / A: Yes — always. We also include a free color consultation so you're confident before we pick up a brush.
- Q: Are you licensed and insured? / A: Yes. Dixon Painting Co. is fully licensed and insured. We're happy to provide documentation upon request.
- Q: What areas do you serve? / A: We're based in Dixon, CA and serve all cities within 20 miles — including Vacaville, Woodland, Fairfield, and Davis.

**Service Area Messaging:** Dixon Painting Co. is based in Dixon, CA and proudly serves homeowners and businesses throughout the surrounding area — including Vacaville, Woodland, Fairfield, Davis, and every community within 20 miles. Same quality, same reliability, wherever you are.

---

### Services Page Copy

**Headline:** Professional Painting Services for Homes and Businesses in Dixon, CA
**Subheadline:** Interior, exterior, cabinets, and commercial — done right the first time.
**Hero Body:** Every painting job we take on starts with a conversation and a free estimate. We assess the space, talk through your goals, and give you a clear price before any work begins. No surprises, no upsells, no mess left behind.
**Primary CTA:** Get a Free Estimate
**Urgency CTA:** Call (916) 612-2126 — We Pick Up

---

### Interior Painting Page Copy

**Headline:** Interior Painting in Dixon, CA — Clean Work, No Mess, Beautiful Finish
**Subheadline:** We protect your floors, furniture, and trim — and leave your rooms looking like new.
**Hero Body:** Interior painting is more than picking a color. It's proper prep, clean lines, and a finish that doesn't show brush marks six months later. Dixon Painting Co. handles everything from walls and ceilings to trim and accent walls — in any room, any size. We work cleanly, move carefully, and leave your home the way we found it (except with a fresh coat of paint).
**Primary CTA:** Get a Free Interior Painting Estimate
**Urgency CTA:** Call (916) 612-2126

---

### Exterior Painting Page Copy

**Headline:** Exterior Painting in Dixon, CA — Built to Handle California Weather
**Subheadline:** Protect your home's exterior with a finish that looks great and lasts for years.
**Hero Body:** California sun and seasonal heat can fade and crack exterior paint faster than you'd expect. Dixon Painting Co. uses premium exterior-grade paints and thorough surface prep to make sure your finish doesn't just look good on day one — it holds up through every season. We handle siding, trim, fascia, and garage doors, and we'll help you choose a color that stands out in the neighborhood for all the right reasons.
**Primary CTA:** Get a Free Exterior Painting Estimate
**Urgency CTA:** Call (916) 612-2126

---

### Cabinet Painting Page Copy

**Headline:** Cabinet Painting in Dixon, CA — Kitchen Refresh Without the Remodel Price Tag
**Subheadline:** Update your kitchen's look for a fraction of what new cabinets cost.
**Hero Body:** New cabinets can cost tens of thousands of dollars. A professional cabinet paint job by Dixon Painting Co. can achieve a similar transformation for dramatically less — and with zero demolition. We sand, prime, and apply a durable factory-smooth finish that holds up to daily kitchen use. Choose any color. Keep your existing layout. Get a kitchen that feels completely new.
**Primary CTA:** Get a Free Cabinet Painting Quote
**Urgency CTA:** Call (916) 612-2126 — Book Your Spot

---

### Commercial Painting Page Copy

**Headline:** Commercial Painting in Dixon, CA — Professional Results, Minimal Disruption
**Subheadline:** We work around your schedule so your business doesn't skip a beat.
**Hero Body:** First impressions matter. Whether it's a retail space, office, or multi-unit property, Dixon Painting Co. delivers professional commercial painting with the reliability your business depends on. We coordinate around your hours — early mornings, evenings, weekends — and we're experienced working in occupied spaces. Clean, efficient, and done when we say it will be.
**Primary CTA:** Request a Commercial Painting Estimate
**Urgency CTA:** Call (916) 612-2126

---

### Gallery Page Copy

**Headline:** Our Work — Before & After Projects by Dixon Painting Co.
**Subheadline:** See the difference a professional paint job makes.
**Hero Body:** Every project in our gallery was completed by our team in Dixon, CA and the surrounding area. Browse interior, exterior, and cabinet painting transformations — then imagine what we can do for your home or business.
**Primary CTA:** Like What You See? Get a Free Estimate
**Urgency CTA:** Call (916) 612-2126

---

### Service Areas Page Copy

**Headline:** Serving Dixon, Vacaville, Woodland, Fairfield, Davis & Beyond
**Subheadline:** Based in Dixon, CA — available anywhere within 20 miles.
**Hero Body:** Dixon Painting Co. is rooted in Dixon, CA, but our work takes us all across the region. We serve homeowners and businesses throughout a 20-mile radius — delivering the same punctual, quality painting service that Dixon residents count on, wherever you are.
**Primary CTA:** Get a Free Estimate in Your Area
**Urgency CTA:** Call (916) 612-2126

**City Page Template** (Vacaville, Woodland, Fairfield, Davis):
> **Headline:** [Service] Contractor in [City], CA | Dixon Painting Co.
> **Body:** Dixon Painting Co. provides professional interior, exterior, and cabinet painting to homeowners and businesses in [City], CA. Our team is local, licensed, and insured — and we offer free estimates with no pressure. Call (916) 612-2126 or fill out our online form to get started.
> **Primary CTA:** Get a Free Estimate in [City]

---

### About Page Copy

**Headline:** Dixon Painting Co. — Local Painters Who Take Pride in the Work
**Subheadline:** We're based in Dixon, CA and we treat every project like it's in our own home.
**Hero Body:** Dixon Painting Co. was built on a simple idea: show up when you say you will, do the job right, and leave the space cleaner than you found it. We're a locally owned painting contractor serving Dixon and the surrounding area — and we care about what our neighbors think of our work, because we live here too. Every estimate is free. Every job starts with honest communication. And every project ends with a walkthrough to make sure you're completely satisfied before we pack up and leave.
**Primary CTA:** Get Your Free Estimate
**Urgency CTA:** Call (916) 612-2126 — Talk to a Real Person

---

### Contact Page Copy

**Headline:** Get Your Free Painting Estimate — No Pressure, No Obligation
**Subheadline:** Fill out the form or call (916) 612-2126 — we'll get back to you the same day.
**Hero Body:** Whether you're ready to book or just getting started, we're happy to talk through your project and give you a clear, honest estimate at no cost. We serve Dixon, CA and all cities within 20 miles.
**Primary CTA:** Send My Estimate Request
**Urgency CTA:** Prefer to call? (916) 612-2126 — we pick up.

---

## Lead Capture Offer

**Recommended Offer:** Free Color Consultation + Estimate
**Offer Headline:** Not Sure What Color to Choose? We'll Help — Free.
**Offer Supporting Copy:** Every estimate from Dixon Painting Co. includes a complimentary color consultation. We'll walk through your space, understand your vision, and help you find the perfect shade before a single brush stroke.
**CTA Button Text:** Get My Free Estimate + Color Consult
**Placement:** Hero section (above fold), sticky header bar, contact page, footer CTA band

---

## What site-designer Should Know

- **Color preference:** TBD — site-designer should pick an industry-appropriate palette. Painting industry defaults: clean whites, bold accent (navy, deep green, or charcoal), warm neutrals. Convey professionalism and craftsmanship.
- **Reference sites:** None provided
- **Tone:** Professional and warm. Approachable but competent. Outcome-focused. No jargon. Confident without being salesy.
- **Key conversion elements:**
  - Phone number in top bar, sticky header (always visible), hero section, footer, and contact page
  - Sticky CTA bar on mobile — `📞 Call Now` + `Get Free Estimate` buttons
  - Lead capture form above fold on homepage and contact page
  - Trust badges (Licensed & Insured, Locally Owned, Free Estimates, 5-star rating) near fold
  - Before/after gallery section on homepage and gallery page
  - Service area city list visible without scrolling on service-areas page
- **Stack notes:** Astro SSG — all pages statically generated. Use `astro:assets` `<Image>` throughout. Limit `client:*` directives to lead capture form only. Use `@astrojs/sitemap` integration.
- **Deployment:** Netlify via GitHub integration. Configure `netlify.toml` for build settings. No environment variables needed (no auth, no DB).

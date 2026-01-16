# 5D Memory Crystal Website Refresh - SPEC.md

**Project:** 5dmemorycrystal.com Website Redesign  
**Client:** SPhotonix Inc.  
**Designer/Developer:** Andrii Pavlov  
**Project Manager:** Denys Chumak  
**Stakeholder:** Caroline (CMO) - Final Approver  
**Created:** January 16, 2026  
**Status:** Phase 1 In Progress  

---

## Table of Contents

1. [Executive Summary](#1-executive-summary)
2. [Business Goals & Success Metrics](#2-business-goals--success-metrics)
3. [Target Audience](#3-target-audience)
4. [Revenue Model & Pricing](#4-revenue-model--pricing)
5. [Branding & Visual Identity](#5-branding--visual-identity)
6. [Content & Messaging](#6-content--messaging)
7. [Site Structure & User Flows](#7-site-structure--user-flows)
8. [Features & Functionality](#8-features--functionality)
9. [Technical Requirements](#9-technical-requirements)
10. [Product Specifications](#10-product-specifications)
11. [SEO & GEO Strategy](#11-seo--geo-strategy)
12. [Timeline & Phases](#12-timeline--phases)
13. [Budget & Scope](#13-budget--scope)
14. [Open Questions for Caroline](#14-open-questions-for-caroline)
15. [Appendix](#15-appendix)

---

## 1. Executive Summary

### Project Overview

Refresh and update [5dmemorycrystal.com](https://www.5dmemorycrystal.com) to:
- Position 5D Memory Crystal as a **high-end luxury product**
- Appeal to both **B2C** (individuals who can spend $3K-$25K+) and **B2B** (luxury brands, watchmakers, archives)
- Maintain existing SEO traction while dramatically elevating visual execution
- Drive B2C traffic to the quiz funnel at `memory-quiz.5dmemorycrystal.com`
- Create dedicated B2B content for luxury partnerships

### Key Principle

> **Each successful B2B case must be documented as a separate page/topic for SEO and GEO optimization.**

### Related Properties

| Property | Purpose | Tech Stack |
|----------|---------|------------|
| 5dmemorycrystal.com | Consumer/B2B brand site | TBD (this project) |
| memory-quiz.5dmemorycrystal.com | B2C conversion funnel | Next.js / Cloud Run |
| sphotonix.com | Corporate/investor site | Separate |

---

## 2. Business Goals & Success Metrics

### Primary Goal

Both B2C and B2B, with **B2C as immediate priority** to prove the model.

### Revenue Targets (By October 2026)

| Segment | Revenue Target | Price per Crystal | Deals Needed | Data Size |
|---------|----------------|-------------------|--------------|-----------|
| **B2C** | $75,000 | $2,000+ | 38 deals | 1GB+ |
| **B2B - Space/Payload** | $100,000 | $4,000 | 25 deals | 1GB+ |
| **B2B - Novelty** | $25,000 | $5,000 | 5 deals | 1GB+ |
| **B2B - Sector 1** | $50,000 | $10,000 | 5 deals | 2GB+ |
| **B2B - Sector 2** | $50,000 | $10,000 | 5 deals | 2GB+ |
| **TOTAL** | **$300,000** | — | **78 deals** | — |

### Revenue Split

- **2026 Target:** 25% B2C / 75% B2B
- **Long-term:** B2B becomes primary revenue driver

### Success Metrics

| Metric | Target |
|--------|--------|
| Quiz completions | 200+/month |
| B2C deposits ($100) | 15-20/month |
| B2C full payments ($3K) | 3-4/month |
| B2B inquiry forms | 5+/month |
| Page load time | <3 seconds |
| Bounce rate | <40% |
| Lighthouse score | 90+ |

### Conversion Funnel Targets

```
Landing Page Views → Quiz Completion: 1-2%
Quiz Completion → Deposit ($100): 5-8%
Deposit → Full Payment ($3K): 75%+
```

---

## 3. Target Audience

### B2C Persona: "Legacy Lauren"

| Attribute | Detail |
|-----------|--------|
| Age | 45-65 |
| Household Income | $500K+ |
| Owns | Luxury watches, art, collectibles |
| Triggers | Milestone birthday, parent's passing, family archive project, estate planning |
| Values | Permanence, craftsmanship, exclusivity, legacy |
| Emotional Drivers | Fear of being forgotten, desire to leave something behind, family connection |

### B2B Persona: Brand Heritage Director

| Attribute | Detail |
|-----------|--------|
| Role | Head of Innovation / Brand Heritage Director |
| Company Type | Luxury maisons, watchmakers, fashion houses, family offices |
| Interests | Archiving brand history, VIP customer gifts, product authentication, sustainability |
| Rational Drivers | 1000+ year durability, no migration costs, no format obsolescence, differentiation |

> ⚠️ **NEEDS CAROLINE INPUT:** Specific B2B decision-maker details and use cases

### Geographic Focus

- **Primary:** United States
- **Secondary:** UK, EU, UAE, Singapore
- **Shipping:** Available globally
- **Language:** English only (multi-language is Phase 2)

---

## 4. Revenue Model & Pricing

### B2C Pricing Tiers

| Tier | Storage | Price | Target Customer |
|------|---------|-------|-----------------|
| Standard | 1GB | $3,000 | Individual memories |
| Premium | 4GB | $8,000-$10,000 | Family archives |
| Collection | Custom | $15,000-$25,000 | Multiple crystals, premium packaging, concierge |

### B2B Pricing

- **No public pricing** on website
- "Contact for enterprise pricing"
- Minimum deal value: $4,000+ per crystal
- Custom quotes based on volume and requirements

### Payment Flow

1. Customer completes quiz
2. $100 refundable deposit (confirms high intent)
3. Design approval process (3-5 days)
4. Full payment ($3,000+)
5. Production (7 days)
6. Shipment (Day 30)

---

## 5. Branding & Visual Identity

### Brand Personality

> **"Quiet luxury meets deep tech."**

Think Leica meets Apple. Confident, understated, substantive. Craftsmanship you can feel.

### Brand Attributes

- Premium, not flashy
- Technological sophistication with emotional warmth
- Heritage and innovation combined
- Exclusivity without elitism

### Visual References (Admired)

| Brand | What We Like |
|-------|--------------|
| leica.com | Product photography, heritage storytelling |
| apple.com | Simplicity, scroll experience, product reveal |
| patek.com | Timelessness, generational messaging |
| rimowa.com | Modern luxury, clean layouts |
| arc'teryx.com | Technical + premium feel |

### What to AVOID

- ❌ Generic Webflow/Squarespace templates
- ❌ Startup landing page aesthetic
- ❌ Heavy stock photography
- ❌ "Web3/crypto" visual language
- ❌ Excessive animations
- ❌ Busy e-commerce layouts

### Existing Brand Guidelines

> ⚠️ **NEEDS CAROLINE INPUT:** Confirm brand guidelines status. Logo exists, but no formal brand book. Andrii has freedom to evolve within "premium tech" direction.

### Photography Requirements

| Type | Status | Notes |
|------|--------|-------|
| Product shots | Exists | Some crystal photography available |
| Lifestyle | Needed | Crystal in home setting, hands holding crystal |
| Detail/Macro | Needed | Close-up of crystal structure, colors under light |
| Packaging | Needed | Unboxing experience, premium cases |

### Video Requirements

| Type | Status | Notes |
|------|--------|-------|
| Product videos | Exists | Some available |
| Hero brand video | Needed | 60s emotional brand story |
| How it works | Needed | Explainer video |
| Testimonials | Needed | Customer stories (when available) |

### Visual Hero Strategy

**Both product AND emotional outcome, sequenced:**
1. Lead with emotional outcome (memories, legacy, family)
2. Reveal product as the solution
3. Product is beautiful but it's about what's inside

---

## 6. Content & Messaging

### Core Message

> ⚠️ **NEEDS CAROLINE INPUT:** Confirm single most important message.
> 
> Draft: **"Your most precious memories, preserved for 1,000+ years."**

### Tagline Evolution

Current: "Preserve your data for Eternity" (functional but cold)

**Proposed options:**
- "Memories that outlast time"
- "A thousand years of you"
- "Legacy, crystallized"

### Content Depth Strategy

| Page | Technical Depth | Tone |
|------|-----------------|------|
| Homepage | Light | Emotional + benefit-focused |
| Technology | Deep | Scientific credibility |
| B2C Product | Medium | Features + emotional outcomes |
| B2B | Medium-Deep | ROI, durability, specifications |

### Common Objections to Address

| Objection | Response Strategy |
|-----------|-------------------|
| "Why $3K for just 1GB?" | It's not about storage size—it's about permanence. Your great-grandchildren will access this. |
| "Will SPhotonix exist in 100 years?" | The crystal doesn't need us to. It's self-contained, readable with standard optical equipment. |
| "Who needs 1000 years?" | Frame as generational: your great-great-grandchildren. Show multi-generational family imagery. |

### Trust Signals (Priority Order)

**Tier 1 - Press/Media:**
- Forbes
- TechRadar
- The Telegraph
- Wired
- TechCrunch

**Tier 2 - Credentials:**
- Prof. Peter Kazansky (inventor, world-leading scientist)
- 30+ years of R&D
- University of Southampton research foundation
- Patents and peer-reviewed publications

**Tier 3 - Social Proof:**
- Customer testimonials (plan for section, populate post-launch)
- B2B case studies (each as separate page for SEO)
- Example crystals gallery (MoonMars Museum, ADNOC, etc.)

### Blog Strategy

- Keep existing blog
- Light refresh for visual consistency
- Add "Press & News" section for media mentions
- Not primary content focus

---

## 7. Site Structure & User Flows

### Information Architecture

```
5dmemorycrystal.com/
├── Home (speaks to both B2C and B2B)
├── How It Works
├── Technology (detailed science)
├── Products & Pricing
│   ├── Personal (B2C)
│   └── Business (B2B overview)
├── Gallery / Our Crystals
├── Case Studies (B2B - individual pages for SEO)
│   ├── /case-study/moonmars-museum
│   ├── /case-study/adnoc
│   └── /case-study/[future-clients]
├── About / Our Story
├── Blog
├── Contact
└── Footer: "A SPhotonix company"
```

### B2C User Flow

```
Homepage 
  → "Preserve Your Memories" CTA
  → Product/Pricing page
  → "Start Your Crystal" CTA
  → Quiz (memory-quiz.5dmemorycrystal.com)
  → Deposit checkout (Stripe)
  → Email confirmation + next steps
```

### B2B User Flow

```
Homepage
  → "For Business" CTA
  → B2B landing section
  → Use cases by industry
  → Case studies (individual pages)
  → "Partner With Us" form / Book a call
  → HubSpot + Slack notification
```

### Navigation Structure

**Primary Nav:**
- How It Works
- Technology
- Pricing
- For Business
- Gallery
- Contact

**CTA Buttons:**
- B2C: "Start Your Crystal" → Quiz
- B2B: "Partner With Us" → Contact form

---

## 8. Features & Functionality

### Must Have (Phase 1)

| Feature | Details |
|---------|---------|
| Responsive design | Mobile-first, all breakpoints |
| Homepage | Hero, value props, trust signals, dual CTAs |
| Product pages | B2C pricing, features, CTA to quiz |
| Technology page | Science explanation, credentials |
| Gallery | Crystal examples with design → result |
| Contact form | Basic inquiry form |
| Newsletter signup | Footer + exit-intent |
| Live chat widget | Intercom or Crisp |
| Analytics | GA4, Meta Pixel, PostHog integration |
| SEO foundations | Meta tags, structured data, sitemap |

### Must Have (Phase 2)

| Feature | Details |
|---------|---------|
| B2B section | Dedicated landing page |
| Case studies | Individual pages per B2B client (SEO) |
| "Book a Call" | Calendly or similar integration |
| Press/News section | Media mentions aggregation |
| Enhanced gallery | Filter by crystal type/size |

### Not in Scope

- ❌ Mobile app
- ❌ Customer portal/dashboard
- ❌ B2B pricing calculator
- ❌ Multi-language support
- ❌ Full quiz redesign (light updates only)
- ❌ E-commerce cart (quiz handles checkout)
- ❌ Account/login system

### Integrations

| System | Purpose | Status |
|--------|---------|--------|
| Stripe | Payments | Via quiz (existing) |
| HubSpot | CRM, leads | Continue |
| Slack | Notifications | Continue |
| GA4 | Analytics | Continue |
| PostHog | Product analytics | Continue |
| Meta Pixel | Ad tracking | Continue |
| Hotjar | Heatmaps | Add |
| Intercom/Crisp | Live chat | Add |

---

## 9. Technical Requirements

### Preferred Stack

| Component | Preference | Notes |
|-----------|------------|-------|
| Framework | Next.js preferred, Webflow acceptable | Consistency with quiz |
| Hosting | Google Cloud Run | Prefer Google services |
| CMS | Headless (Sanity, Contentful) or Webflow CMS | Easy content updates |
| Domain | 5dmemorycrystal.com | Keep existing |
| SSL | Required | Already in place |

### Performance Targets

| Metric | Target |
|--------|--------|
| Lighthouse Performance | 90+ |
| Largest Contentful Paint (LCP) | <2.5s |
| Cumulative Layout Shift (CLS) | <0.1 |
| First Input Delay (FID) | <100ms |
| Time to Interactive | <3.5s |

### Accessibility

- **Standard:** WCAG 2.1 AA minimum
- Semantic HTML
- Keyboard navigation
- Screen reader compatible
- Sufficient color contrast

### Browser Support

- Chrome (last 2 versions)
- Safari (last 2 versions)
- Firefox (last 2 versions)
- Edge (last 2 versions)
- Mobile Safari (iOS 14+)
- Chrome Mobile (Android 10+)

---

## 10. Product Specifications

### Crystal Shapes & Sizes

| Shape | Available Sizes |
|-------|-----------------|
| Round | 2.5 cm, 5 cm |
| Square | 2.5 cm, 5 cm, 7.5 cm |
| Rectangular | Custom dimensions |

### Artwork Guidelines

**Color Format:**
- Any colors permitted in artwork
- Appears black/white/grayscale to naked eye
- Vivid color visible only under microscope

**Best Image Types:**
- 2D images and QR codes work best
- 3D images and holograms are NOT as effective

**File Types Accepted:**
- .eps, .png, .jpg, .pdf

**Artwork Area Calculation:**
```
Maximum Artwork Diameter/Side = Crystal Dimension - 2mm
(1mm border required on each side)

Examples:
- 2.5 cm Round: Max artwork diameter = 23mm
- 5 cm Square: Max artwork side = 48mm
```

### Data Storage Requirements

| Requirement | Specification |
|-------------|---------------|
| 1GB data storage | Requires 56 mm² free from artwork |
| Artwork + Data gap | Minimum 0.3mm (300 microns) |
| Decoding block | 1mm x 1mm (code-to-decode info) |
| Serial number | Unique SPhotonix serial, very small |

### Optional Add-ons

- Graphic design support (hourly rate)
- Designer display cases (jewelry box style)
- Certificate of Authenticity (included)

---

## 11. SEO & GEO Strategy

### Protected Keywords

- "5D memory crystal"
- "5D optical storage"
- "SPhotonix"
- "eternal data storage"

### Target Keywords

- "luxury data storage"
- "permanent memory storage"
- "legacy preservation"
- "generational data storage"
- "archival storage technology"

### B2B Case Study SEO Strategy

> **Critical:** Each successful B2B case must have its own dedicated page for SEO and GEO optimization.

**URL Structure:**
```
/case-study/moonmars-museum
/case-study/adnoc-heritage
/case-study/[client-name]
```

**Each page includes:**
- Client background
- Challenge/need
- Solution provided
- Results/outcomes
- Technical specifications used
- Testimonial quote
- Related case studies
- CTA to contact

### Structured Data

- Organization schema
- Product schema
- FAQ schema
- Article schema (blog/case studies)
- Review schema (when testimonials available)

> ⚠️ **NEEDS CAROLINE INPUT:** Additional SEO keyword targets

---

## 12. Timeline & Phases

### Overview

| Phase | Duration | Focus | Budget |
|-------|----------|-------|--------|
| Phase 1 | Weeks 1-4 | B2C homepage + product pages | $2,750 (PAID) |
| Phase 2 | Weeks 5-8 | B2B section + case studies | $2,750 |
| Phase 3 | Weeks 9-10 | Quiz updates + refinements | $2,750 |

### Phase 1 Deliverables (Current)

**Budget:** $2,750 (50 hours)  
**Status:** In Progress

- [ ] Website design strategy research
- [ ] Website design concept (Figma)
- [ ] Homepage design & development
- [ ] Product/Pricing page
- [ ] Technology page
- [ ] Basic gallery
- [ ] Contact page
- [ ] Mobile responsive
- [ ] Analytics integration (GA4, Meta Pixel)
- [ ] Deployment to Cloud Run

### Phase 2 Deliverables

**Budget:** $2,750  
**Status:** Pending Phase 1 completion

- [ ] B2B dedicated section
- [ ] Case study template
- [ ] 2-3 case study pages (SEO optimized)
- [ ] "Book a Call" integration
- [ ] Press/News section
- [ ] Enhanced gallery with filters
- [ ] HubSpot form integration

### Phase 3 Deliverables

**Budget:** $2,750  
**Status:** Future

- [ ] Quiz visual alignment with new site
- [ ] Light quiz UI updates
- [ ] Final refinements
- [ ] Performance optimization
- [ ] Documentation & handoff

### Review Process

> ⚠️ **NEEDS CAROLINE INPUT:** Confirm approval workflow

**Proposed:**
- Caroline = Final approver
- Denys = Technical review
- 2 rounds of design revisions
- 1 round of development revisions

---

## 13. Budget & Scope

### Budget Summary

| Phase | Hours | Rate | Total | Status |
|-------|-------|------|-------|--------|
| Phase 1 | 50 | $55/hr | $2,750 | ✅ PAID |
| Phase 2 | 50 | $55/hr | $2,750 | Pending |
| Phase 3 | 50 | $55/hr | $2,750 | Future |
| **Total** | **150** | — | **$8,250** | — |

### What's Included

- Website design strategy research
- Website design concept (Figma files)
- Website content production assistance
- Website development
- Deployment
- Source files handoff
- Light quiz updates (Phase 3)

### What's Excluded

- Mobile app development
- Customer portal/dashboard
- Complete quiz redesign
- Multi-language support
- Ongoing maintenance (separate agreement)
- Ad creative production
- Video production
- Professional photography

### Post-Launch Maintenance

- **Minor updates:** Denys/internal team
- **Major changes:** New SOW with Andrii

---

## 14. Open Questions for Caroline

The following items need Caroline's input before finalizing:

### Branding & Messaging

| # | Question | Current Draft |
|---|----------|---------------|
| 8 | Partnerships to feature on launch? | No names yet, prepare section |
| 18 | Existing brand guidelines to follow? | Logo exists, no formal book |
| 19 | Evolution of current site or complete departure? | Evolution with elevation |
| 25 | Single most important message? | "Your most precious memories, preserved for 1,000+ years" |

### B2B Strategy

| # | Question | Current Draft |
|---|----------|---------------|
| 10 | Who is the B2B decision-maker? | Head of Innovation / Brand Heritage Director |
| 12 | Specific B2B use cases to highlight? | Watches, fashion, family offices |

### Operations

| # | Question | Current Draft |
|---|----------|---------------|
| 30 | Customer testimonials available? | Limited, plan for section |
| 48 | SEO keyword targets? | "luxury data storage," "permanent memory storage" |
| 53 | Review/approval process? | Caroline final, Denys technical, 2 design + 1 dev revision |

---

## 15. Appendix

### A. Example Crystals

**MoonMars Museum Crystal**
- Shape: Round
- Content: Space exploration imagery, museum branding
- Use case: Archival / exhibition piece

**ADNOC Heritage Crystal**
- Shape: Round  
- Content: UAE heritage, corporate branding, "Eternal Journey of Generations"
- Use case: B2B corporate gift / archive

### B. Technical Diagrams

```
Crystal Dimension Reference:

ROUND          SQUARE         RECTANGULAR
┌─────┐        ┌─────┐        ┌───────┐
│  B  │        │  B  │        │B1│ B  │
│ ┌─┐ │        │┌───┐│        │┌─┴───┐│
│A│ │A│        ││   ││        ││     ││
│ └─┘ │        │└───┘│        │└─────┘│
│  C  │        │  C  │        │   C   │
└─────┘        └─────┘        └───────┘

B = A - 2mm (1mm border each side)
C = Crystal thickness
```

### C. File Handoff Checklist

Upon project completion, Andrii delivers:

- [ ] Figma design files (full access)
- [ ] Source code repository
- [ ] Deployment documentation
- [ ] CMS access credentials
- [ ] Analytics verification
- [ ] Training session (30 min)

### D. Related Documents

- [SPhotonix B2C Ad Projection](./sphotonix-b2c-ad-projection.csv)
- [Quiz Repository](https://github.com/sphotonix/memory-crystal-quiz)
- [General Artwork Guidelines](https://5dmemorycrystal.com/artwork-guidelines)

---

## Revision History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | 2026-01-16 | Denys Chumak | Initial draft |

---

**Document Status:** Draft - Awaiting Caroline's Input on Flagged Items

**Next Steps:**
1. Get Caroline's answers to Section 14 questions
2. Finalize SPEC.md
3. Share with Andrii to begin Phase 1 work

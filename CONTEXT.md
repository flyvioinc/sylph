# Flyvio — Company Context

> Loaded automatically in every Claude session when this repo is mounted.
> Keep accurate. Update when the company materially changes.

## What Flyvio Is

Flyvio Inc. is a Delaware C-Corp building **Traveo** — an open-core corporate travel 
platform for Travel Management Companies. The platform has two products:

1. **Jabiru** (OBT) — the open-source online booking tool that corporate travelers 
   use to search, book, and manage business trips. Licensed under Apache 2.0.
2. **Navira** (API Gateway) — the proprietary connectivity layer that normalizes 
   content from GDS platforms (Amadeus, Travelport, Sabre) and NDC airline sources 
   (Airlink/Accelya, Aegean, others) into a single clean API. This is the commercial 
   moat.

The **Traveo** brand is the market-facing name for the platform. Flyvio Inc. is the 
legal and technology entity. Traveo Services LLC is a separate Florida LLC operating 
a travel services business (crew travel management, workforce lodging, corporate 
travel consulting) that runs in parallel.

**One-liner:** Traveo is the first open-source corporate OBT with a proprietary 
GDS/NDC gateway — built for Travel Management Companies that are done being held 
hostage by closed platforms.

## The Open-Core Model

The business follows the open-core model refined by GitLab, Elastic, HashiCorp, 
and Sentry — adapted for corporate travel.

### Open Source (Apache 2.0) — Jabiru OBT
- Traveler booking UI (web + mobile)
- Core policy engine (rules, caps, approval routing)
- PNR workflow and booking orchestration
- Reference GDS connector (single Amadeus starter)
- Self-serve admin panel for small teams
- Basic spend and booking reporting
- Public REST API spec and developer SDK

### Proprietary & Paid — Navira Gateway + Traveo Cloud
- Full Navira API Gateway (Amadeus + Travelport + Sabre)
- NDC channel integrations (Airlink/Accelya, Aegean, others)
- Managed SaaS hosting (Traveo Cloud)
- Enterprise SSO (SAML 2.0), SCIM, audit logs
- Advanced reporting, forecasting, benchmarking
- Duty of care: traveler tracking, alerts, crisis response
- AI-driven dynamic policy and spend optimization
- Multi-tenant white-label for TMCs
- Priority SLAs, dedicated support, onboarding
- Professional services and custom connector development

**The rule that cannot be broken:** Once a feature is open-sourced, it never moves 
to closed. The Apache 2.0 OBT core will never be re-licensed to a more restrictive 
license. If economics need to change, we add paid value on top — never remove value 
from the community layer.

## The Problem We Solve

TMCs need an OBT to serve their corporate customers, but today's options — SAP 
Concur, Amadeus Cytric, Sabre GetThere, Deem — are closed, rigid, slow to evolve, 
and architected for lock-in. TMCs cannot customize the booking experience without 
expensive professional services, cannot easily integrate NDC content, and have no 
leverage with incumbent vendors.

The result: TMCs lose deals to competitors with better tech, and corporate travelers 
get a clunky experience that pushes them to book outside policy.

Three structural shifts have created the opening Traveo is built to exploit:
1. NDC has commoditized airline content access — certifications are achievable by 
   a well-resourced small team, and airlines are actively incentivizing new 
   distribution partners.
2. Corporate buyers have lost patience with closed platforms — 39% of buyers 
   evaluating a TMC change cite technology as their primary driver.
3. Open source is now the default trust signal for technical buyers — the ability 
   to say "inspect the code, fork it if you want, we do not hold you hostage" is 
   a structural advantage no incumbent can offer.

## Competitive Moat

The moat is not the OBT code — it is five things that cannot be forked:
1. **Certifications and airline relationships** — GDS and NDC certifications are 
   legal and commercial relationships. A competitor forking Jabiru still has zero 
   connectivity.
2. **Production track record** — TMC buyers are risk-averse. Live bookings at named 
   customers are worth more than any pitch deck.
3. **Community and ecosystem** — an active open-source community creates network 
   effects competitors start from zero on.
4. **Data network effects** — every booking through Traveo Cloud creates aggregate 
   insights no self-hosted OBT can produce.
5. **Trademark and brand** — "Traveo" and "Meridian" trademarked in US and key 
   EMEA markets. Any fork cannot use the brand.

## ICP (Ideal Customer Profile)

**Primary — Mid-Market TMCs (Year 1 focus)**
- US-based TMCs with annual transaction volume $50M–$500M
- Too large to go without an OBT; too small to build their own
- Currently paying per-booking or per-seat fees to legacy OBT vendors
- Buying trigger: OBT contract renewal, vendor dissatisfaction, lost corporate 
  client citing technology
- Decision maker: TMC CEO, CTO, or Head of Technology
- Sales cycle: 3–6 months

**Secondary — Direct Corporates (Year 2 focus)**
- Mid-to-large corporations ($500M–$5B revenue) with managed travel programs
- Specific compliance, data sovereignty, or API access requirements
- ACV: $50K–$200K+; sales cycle: 6–12 months

**Strategic — Airlines (Year 2–3)**
- Airlines wanting a branded corporate booking portal for top corporate accounts
- Airlink is the prototypical example
- High-value, high-complexity; significant professional services component

**User:** Corporate travelers and travel arrangers at the TMC's client companies.

## Pricing Model

Hybrid band model: flat platform fee covering a booking volume band, plus low 
per-booking overage on excess.

| Tier | Target | Annual Fee | Booking Band | Overage |
|------|--------|------------|--------------|---------|
| Community | Developers, very small TMCs | Free | 500 bookings | Self-host only |
| Growth | Small TMCs | $18,000/yr | 5,000 bookings | $2.50/booking over |
| Professional | Mid-market TMCs | $48,000/yr | 25,000 bookings | $1.75/booking over |
| Enterprise | Large TMCs, corporates, airlines | From $120,000/yr | Custom | Custom |
| Airline/OEM | Airlines with corporate portals | Custom + setup | Revenue-share | Custom |

**The competitive price case:** A TMC processing 15,000 bookings/year pays $120K+ 
with a legacy vendor at $8/booking. Traveo Professional is $48K — a 60% cost 
reduction with full API access and no lock-in.

## Go-To-Market Strategy

**Two parallel tracks:**

**Track 1 — Open-source community GTM**
- Jabiru OBT GitHub repo as top of funnel
- Year 1 community goal: 500 GitHub stars, 50 active community members, 
  10 self-hosted deployments
- Launch on Hacker News "Show HN", PhocusWire, Skift, BTN
- Weekly public changelogs; monthly "state of Meridian" blog post
- Conference presence: GBTA Convention, The Beat Live, BTN Forum

**Track 2 — Direct sales, TMC-first**
- Founder-led sales in Year 1
- Target list: 50–80 US mid-market TMCs filtered for contract renewals 
  within 12–18 months
- Outreach: warm, personalized LinkedIn from founder profile — not automated sequences
- Pilot: 60-day paid pilot at $2,000–$3,000 flat for first 5 customers
- Convert to full annual subscription at pilot completion
- Reference: named case study and reference call authorization at contract signing

## Entity Structure

| Entity | Type | Purpose |
|--------|------|---------|
| Flyvio Inc. | Delaware C-Corp | Technology IP, Jabiru OBT, Navira Gateway, future fundraising |
| Traveo Services LLC | Florida LLC | TMC services: crew travel management, workforce lodging, travel consulting |

Both entities are active. Traveo Services LLC generates current operating revenue. 
Flyvio Inc. holds all technology IP and will begin accepting technology revenue 
in February 2028.

**Important:** No commercial technology revenue (OBT licenses, gateway fees, 
Traveo Cloud subscriptions) is collected before February 2028. All current 
revenue flows through Traveo Services LLC only.

## Anthropic Partnership Strategy

Flyvio is pursuing Anthropic partnership through two programs:

1. **Anthropic Startups Program** (apply first — claude.com/startups)
   Better fit for a solo founder; no 10-person team requirement.
   Apply once the Claude policy compliance checker prototype is built.

2. **Claude Partner Network** (apply second — claude.com/partners)
   Apply once a second team member completes Academy courses alongside Rastko.

**The differentiating narrative:** No incumbent OBT — SAP Concur, Cytric, 
GetThere, Deem — can credibly claim to be AI-native. Traveo is built AI-native 
from day one, with Claude Code accelerating development and Claude embedded 
directly in the product layer.

**Priority Claude integrations to build:**
- Travel policy compliance checker (first prototype — 2–3 day Claude Code project)
- Itinerary optimization
- Fare rule explanation in plain language
- AI travel assistant (conversational booking support)
- Supplier negotiation analysis

**Academy courses to complete (admin@flyvio.io):**
1. Building Applications with the Claude API — DO FIRST
2. Introduction to Model Context Protocol (MCP)
3. Claude Code in Action
4. Agent Skills

## Geographic Sequencing

| Phase | Geography | Timing |
|-------|-----------|--------|
| Phase 1 | United States | Year 1 (2028) |
| Phase 2 | United Kingdom + Ireland | Year 2 Q1 |
| Phase 3 | Western Europe (DE, FR, NL, Nordics) | Year 2 Q3 |
| Phase 4 | Middle East + Africa | Year 3 |

## Financial Overview

**Pre-launch (now — Jan 2028):**
- Revenue: Traveo Services LLC TMC services only ($40K–$180K/year target)
- Technology revenue: $0 (intentional — February 2028 start)

**Post-launch targets:**
| Year | Paying TMC Customers | Total Revenue |
|------|---------------------|---------------|
| 2028 (Year 1) | 3–6 | $210K–$380K |
| 2029 (Year 2) | 10–16 | $600K–$1.0M |
| 2030 (Year 3) | 22–35 | $1.54M–$2.52M |

Seed raise trigger: $300K+ ARR + 4 paying logos.

## Current Product Status

- **Navira (API Gateway):** NDC integrations implemented for Airlink (4Z) on 
  Accelya FLX Select NDC v21.3. Air shopping, offers, order create, change, 
  seats, services, and cancellation implemented. Known issue: 422 error on 
  multi-passenger round-trip bookings — resolution pending (server-side, 
  Navira team to investigate).
- **Aegean (A3):** Integration underway; testing in progress.
- **Ethiopian (ET):** Planned on same Accelya FLX Select stack.
- **Jabiru (OBT):** In development. Renamed from Meridian OBT.
- **GDS:** Amadeus certification in planning; Travelport and Sabre to follow.

## Key Milestones

**Immediate (this month):**
- Traveo Services LLC and Flyvio Inc. both incorporated ✓ (or in progress)
- NDC sandbox credentials requested under Flyvio Inc.
- Trademark applications filed for "Traveo" and "Meridian"
- Michigan attorney retained for legal review
- Greek directorship resignation filed

**Month 3–9:**
- Jabiru on GitHub (pending legal clearance)
- Aegean NDC integration live
- Traveo Services: 2–3 corporate clients, $4K–$6K/month revenue
- Amadeus certification initiated

**Month 9–15:**
- 200+ GitHub stars; 25+ community members
- Travelport certification application submitted
- 5–10 design partner TMC conversations underway

**Month 15–21:**
- Amadeus and Travelport certifications complete
- 500+ GitHub stars
- 3–5 pilot agreements signed (effective Feb 2028)
- Seed round deck prepared

**February 1, 2028:**
- Commercial launch
- 3–5 pilot TMCs go live on day one
- Seed round announcement

## Team

- **Rastko** — Founder, Flyvio Inc. (admin@flyvio.io). Solo founder. 
  Building Navira and Jabiru end-to-end with Claude Code.

## Key Terminology

| Term | Definition |
|------|------------|
| Jabiru | Flyvio's open-source OBT product (formerly Meridian OBT) |
| Navira | Flyvio's proprietary API gateway (formerly Meridian API) |
| Traveo | The market-facing brand name for the platform |
| TMC | Travel Management Company — Flyvio's direct customer |
| OBT | Online Booking Tool — the self-service booking interface |
| NDC | New Distribution Capability — IATA's modern airline distribution standard |
| GDS | Global Distribution System — legacy airline content pipes (Amadeus, Sabre, Travelport) |
| Accelya FLX Select | NDC platform used by Airlink (4Z), Aegean (A3), Ethiopian (ET) |
| 4Z | IATA code for Airlink — first live NDC integration |
| A3 | IATA code for Aegean Airlines — second NDC integration in progress |

## Standing Instructions for Claude

- Default language: English
- Tone: direct, technical, practical — written for TMC operators and corporate 
  travel professionals who know the industry. No generic SaaS fluff 
  ("revolutionize", "unleash", "transform", "game-changing").
- The open-source angle is a core differentiator — surface it for TMC buyers; 
  de-emphasize for corporate travelers who don't care about it.
- "Flyvio" is the legal entity; "Traveo" is the market brand; "Jabiru" and 
  "Navira" are the product names. Use the right name for the right context.
- TMC, OBT, NDC, GDS are uppercase acronyms; expand on first use in any 
  external-facing piece.
- Always apply brand guidelines for external-facing content.
- Read `_insights.md` in the relevant folder before generating content.
- Rastko is the sole decision-maker — when in doubt, flag for him rather 
  than guessing.
- No commercial technology commitments, contracts, or revenue collection 
  before February 2028. Traveo Services LLC handles all current revenue.
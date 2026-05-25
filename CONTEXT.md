# Flyvio - Company Context

> Loaded automatically in every Claude session when this repo is mounted.
> Keep accurate. Update when the company materially changes.

## What Flyvio is

Flyvio is a travel tech company building an **open source Online Booking Tool (OBT)** and an **airline NDC connector** for Travel Management Companies. TMCs license Flyvio and deploy it to their own corporate customers, who use it to search, book, and manage business trips.

The product has two pieces:
1. **OBT** — the booking interface and workflow engine that corporate travelers use end-to-end.
2. **NDC connector** — an integration layer that pulls airline content (fares, ancillaries, rich content) directly from carriers via the IATA NDC standard, rather than relying solely on legacy GDS pipes.

Being **open source** is a deliberate wedge: TMCs today are locked into closed, inflexible OBT vendors. Flyvio gives them a platform they can extend, self-host, and tailor to their corporate clients without waiting on a vendor roadmap.

**One-liner:** Flyvio is the open source online booking tool for Travel Management Companies.

## The problem you solve

TMCs need an OBT to serve their corporate customers, but today's options are closed, rigid, and slow to evolve. TMCs can't customize the booking experience for individual corporate clients without expensive professional services, can't easily integrate new airline content (especially NDC), and have no leverage with incumbent OBT vendors. The result: TMCs lose deals to competitors with better tech, and corporate travelers get a clunky booking experience that pushes them to book outside policy.

Flyvio solves this by being open source and NDC-native from day one — TMCs can run it, extend it, and brand it for each of their corporate clients.

## How it works

Flyvio is licensed to TMCs, who deploy it for their corporate customers. End users (business travelers and travel arrangers at the TMC's client companies) log in to:

- Search flights, hotels, and rail with content from NDC-connected airlines plus traditional sources
- Apply company-specific travel policy at search and booking time
- Book trips, manage approvals, and handle changes/cancellations
- Sync itineraries to calendars, expense systems, and traveler profiles

The TMC owns the deployment, the branding, and the integrations. Flyvio provides the platform.

## ICP (Ideal Customer Profile)

- **Primary:** Travel Management Companies (TMCs) serving corporate clients — from regional independents up to mid-market global TMCs that want an alternative to incumbent OBT vendors.
- **Buyer:** TMC owners, Heads of Technology / Heads of Product at TMCs, or senior commercial leaders evaluating their OBT stack.
- **User:** Corporate travelers and travel arrangers at the TMC's client companies — the people who actually search, book, and change trips day to day.

## Integrations

- **Airline content:** direct NDC connections to carriers (the core integration surface today)
- Other integrations (hotels, rail, expense, HRIS, SSO) will be added as the product matures

## Team

- **Rastko** - Founder (admin@flyvio.io). Solo founder building Flyvio end-to-end.

## Company

- Founded: 2026
- Stage: Pre-seed, in development, no external funding
- Locations: Aventura, FL, USA
- Website: none yet (stealth)
- GitHub: not public yet (OBT will be open source at launch)

## Key terminology

| Term | Definition |
|------|-----------|
| TMC | **Travel Management Company** — an agency that manages business travel on behalf of corporate clients (booking, policy enforcement, reporting, duty of care). Flyvio's direct customer. |
| OBT | **Online Booking Tool** — the self-service web app corporate travelers and arrangers use to search, book, and manage business trips. Flyvio's core product. |
| NDC | **New Distribution Capability** — IATA's modern XML-based airline distribution standard. Lets sellers access airline content (fares, ancillaries, rich media) directly from carriers, supplementing or bypassing legacy GDS. |
| GDS | **Global Distribution System** — the legacy airline content pipes (Amadeus, Sabre, Travelport). Still the dominant source of inventory; NDC is the alternative/complement. |
| Corporate traveler | The end user — an employee at the TMC's client company who books trips through the OBT under their employer's travel policy. |
| Travel arranger | A non-traveling employee (often an EA or admin) who books on behalf of others. Power user of the OBT. |

## Standing instructions for Claude

- Default language: English (unless explicitly for a different audience)
- Tone: direct, technical, practical — written for TMC operators and corporate travel professionals who already know the industry. Avoid generic SaaS fluff ("revolutionize", "unleash", "transform").
- The open source angle is a core differentiator — surface it when relevant, but don't lead with it for every audience (corporate travelers don't care; TMC buyers do).
- "Flyvio" is the brand name — capitalized as a proper noun (Flyvio), not all-lowercase or all-caps.
- TMC, OBT, NDC, GDS are written as uppercase acronyms; expand on first use in any external-facing piece.
- Always apply brand guidelines for external-facing content
- Read `_insights.md` in the relevant folder before generating content
- Rastko is the solo founder and CAO — when in doubt about a decision, flag it for him rather than guessing.

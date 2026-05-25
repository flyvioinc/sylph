---
name: Mailbox setup
description: Flyvio + Traveo Services mailboxes across two M365 tenants — current connection state and how agents should access each.
type: project
---

Flyvio operates **two separate Microsoft 365 tenants**, one per legal entity. Claude Code supports only one M365 MCP connector instance, so the second tenant is accessed via a Claude_in_Chrome browser bridge instead.

| Mailbox | Tenant | Entity | Agent access method |
|---------|--------|--------|---------------------|
| `admin@flyvio.io` | `flyvio.onmicrosoft.com` | Flyvio Inc. (Delaware C-Corp) | **Native M365 MCP** — UUID `7264b804-8b69-4c8c-9a9b-ef75083c145d` |
| `rastkoilic@flyvio.onmicrosoft.com` | `flyvio.onmicrosoft.com` | Flyvio Inc. (M365 admin acct) | Same MCP; receives MS billing only |
| `sales@traveo.us` | `traveo.us` (separate tenant) | Traveo Services LLC (Florida LLC) | **Not connected** — Rastko handles manually for now |

## How agents should use each

- **Flyvio Inc. matters** (Jabiru, Navira, NDC partners, investors, technology legal): use the native M365 MCP, default from `admin@flyvio.io`.
- **Traveo Services LLC matters** (TMC services, crew travel, workforce lodging, consulting clients, outbound to those prospects): the `sales@traveo.us` mailbox is **out of scope for agents today** — Rastko reads, drafts, and sends manually. CoS briefings will not include Traveo Services LLC inbox or calendar items until a connection path is established.
- **Never cross-post.** A Flyvio Inc. matter must not be sent from `traveo.us` and vice versa. The two-entity separation is intentional and legally meaningful.

## If we revisit sales@traveo.us coverage later

Three options were evaluated and skipped on 2026-05-25:

1. **Second M365 MCP connector** — blocked: Claude Code currently supports only one M365 connector per install.
2. **Claude_in_Chrome bridge to OWA** — viable but requires installing the Claude for Chrome extension, keeping Chrome running, and staying signed into OWA as `sales@traveo.us`. Read-only for the agent.
3. **B2B cross-tenant delegation** — heaviest Azure AD setup; would give native MCP access but adds operational complexity.

Pick one and update this file + `agents/chief-of-staff/PROMPT.md` when the time comes.

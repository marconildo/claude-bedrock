---
type: actor
name: "Payments Lifecycle"
aliases: ["Payments Lifecycle API v2", "payments-lifecycle"]
category: "api"
description: "New unified Payments platform API serving all brands (Stone, Ton, Pagar.me) with brand-agnostic entity management"
repository: ""
stack: ""
status: "in-development"
team: ""
criticality: "very-high"
pci: false
known_issues: []
sources:
  - url: "https://allstone.atlassian.net/wiki/spaces/RCON/pages/8283750802/Introdu+o+a+Nova+modelagem#PaymentProfile"
    type: "confluence"
    synced_at: 2026-04-14
updated_at: 2026-04-14
updated_by: "preserve@agent"
tags: [type/actor, status/in-development, domain/payments]
---

<!-- Zettelkasten role: permanent note -->
<!-- Links in the body must have context -->

# Payments Lifecycle

> New unified Payments platform API (`api.stone.com.br/payments-lifecycle/v2/`) serving all brands with brand-agnostic entity management.

## Details

| Field | Value |
|---|---|
| Repository | TBD |
| Stack | TBD |
| Status | in-development |
| Criticality | very-high |
| PCI | no |
| Team | TBD |

## Key Endpoints

- `POST /v2/onboarding` — Client creation (replaces per-brand flows)
- `POST /v2/payment-profile/` — PaymentProfile creation
- `POST /v2/payment-profile/{id}/poi` — POI creation within a PaymentProfile
- `GET /v2/payment-profile/{id}/` — Query processing config and settlement bank data
- `PUT /v2/payment-profile/{id}/poi_type` — Update transactional configurations
- `PUT /v2/agreements/{id}/` — Update commercial conditions (called by [[distribution]])
- `GET /v2/legacy-identifiers/filter` — Retrocompatibility: lookup between old and new identifiers

## Dependencies

- Depends on: [[identity]] (cadastral data via StoneAccount/Legal Entity)
- Depends on: [[distribution]] (commercial conditions via ActiveOffer)

## Related Topics

- [[2026-04-feature-new-payments-modeling]] — New unified entity model replacing legacy per-brand structures

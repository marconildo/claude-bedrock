---
type: actor
name: "Distribution"
aliases: ["Distribution Service"]
category: "api"
description: "Service responsible for managing commercial conditions (ActiveOffer), pricing plans, and fee distribution to Payments"
repository: ""
stack: ""
status: "active"
team: ""
criticality: "high"
pci: false
known_issues: []
sources:
  - url: "https://allstone.atlassian.net/wiki/spaces/RCON/pages/8283750802/Introdu+o+a+Nova+modelagem#PaymentProfile"
    type: "confluence"
    synced_at: 2026-04-14
updated_at: 2026-04-14
updated_by: "preserve@agent"
tags: [type/actor, status/active, domain/payments]
---

<!-- Zettelkasten role: permanent note -->

# Distribution

> Service managing commercial conditions (ActiveOffer), pricing plans, and fee updates. In the new payments model, Distribution owns the client's active commercial offer and pushes updates to [[payments-lifecycle]] via `PUT /v2/agreements/{id}/`.

## Details

| Field | Value |
|---|---|
| Repository | TBD |
| Stack | TBD |
| Status | active |
| Criticality | high |
| PCI | no |
| Team | TBD |

## Dependencies

- Depended by: [[payments-lifecycle]] (commercial conditions flow via ActiveOffer)

## Related Topics

- [[2026-04-feature-new-payments-modeling]] — Distribution becomes the source of truth for commercial conditions in the new platform

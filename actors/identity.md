---
type: actor
name: "Identity"
aliases: ["Identity Service"]
category: "api"
description: "Service responsible for cadastral data management via StoneAccount and Legal Entity"
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

# Identity

> Service managing cadastral data (registration, document, address) via StoneAccount and Legal Entity. In the new payments model, cadastral data queries are redirected from [[payments-lifecycle]] to Identity instead of being stored in the payments domain.

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

- Depended by: [[payments-lifecycle]] (cadastral data queries via StoneAccount/Legal Entity)

## Related Topics

- [[2026-04-feature-new-payments-modeling]] — Identity becomes the source of truth for cadastral data, decoupling it from Payments

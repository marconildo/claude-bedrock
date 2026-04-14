---
type: actor
name: "MundiPagg Lifecycle"
aliases: ["MundiPagg Lifecycle API", "Ton Lifecycle"]
category: "api"
description: "Legacy Ton lifecycle service handling merchant and agreement management"
repository: ""
stack: ""
status: "deprecated"
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
tags: [type/actor, status/deprecated, domain/payments]
---

<!-- Zettelkasten role: permanent note -->

# MundiPagg Lifecycle

> [!warning] Deprecated
> Being replaced by [[payments-lifecycle]] as part of the [[2026-04-feature-new-payments-modeling]].

> Legacy Ton lifecycle service at `api.mundipagg.com/lifecycle/v1/` handling merchant management and agreement operations.

## Details

| Field | Value |
|---|---|
| Repository | TBD |
| Stack | TBD |
| Status | deprecated |
| Criticality | high |
| PCI | no |
| Team | TBD |

## Legacy Endpoints

- `POST /lifecycle/v1/onboarding` — Client creation (Ton)
- `POST /lifecycle/v1/agreements/` — Agreement creation
- `GET /lifecycle/v1/merchants/{id}` — Query merchant data
- `GET /lifecycle/v1/agreements/{id}` — Query agreement data

## Related Topics

- [[2026-04-feature-new-payments-modeling]] — Replacement by the new unified platform

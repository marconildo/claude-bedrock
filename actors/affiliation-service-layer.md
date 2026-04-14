---
type: actor
name: "Affiliation Service Layer"
aliases: ["Affiliation Service", "ASL"]
category: "api"
description: "Legacy Stone affiliation service handling merchant creation, capture methods, bank accounts, and card brand configuration"
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

# Affiliation Service Layer

> [!warning] Deprecated
> Being replaced by [[payments-lifecycle]] as part of the [[2026-04-feature-new-payments-modeling]].

> Legacy Stone affiliation service at `affiliation-service-layer.qa.stone.com.br` handling merchant creation, capture method updates, bank accounts, and card brand configuration.

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

- `/Merchant/MerchantService.svc/merchant/affiliate/` — Merchant creation
- `/Merchant/MerchantService.svc/merchant/updatecapturemethod/` — Update capture method
- `/Merchant/MerchantService.svc/merchant/listmerchant/` — Query merchant data
- `/Merchant/MerchantService.svc/merchant/listbankaccounts/` — Query bank accounts
- `/Merchant/MerchantService.svc/merchant/updatemerchantmdr/` — Update MDR
- `/Merchant/MerchantService.svc/merchant/updateprepaymentconfiguration/` — Update prepayment config

## Related Topics

- [[2026-04-feature-new-payments-modeling]] — Replacement by the new unified platform

---
type: fleeting
title: "Pagar.me APIs (Legacy)"
aliases: ["Pagar.me Legacy APIs"]
source: "teach"
captured_at: 2026-04-14
status: "raw"
promoted_to: ""
sources:
  - url: "https://allstone.atlassian.net/wiki/spaces/RCON/pages/8283750802/Introdu+o+a+Nova+modelagem#PaymentProfile"
    type: "confluence"
    synced_at: 2026-04-14
updated_at: 2026-04-14
updated_by: "preserve@agent"
tags: [type/fleeting, status/raw, domain/payments]
---

<!-- Zettelkasten role: fleeting note -->

# Pagar.me APIs (Legacy)

> Raw information capture. Source: `confluence`.

## Content

Group of legacy Pagar.me APIs mentioned in the new payments modeling documentation. Multiple services are involved:

- `api.pagar.me/salesforce/v1/customers/` — Customer creation (Salesforce integration)
- `api.pagar.me/bigbang/v1/customers/` — Customer creation (BigBang)
- `api.pagar.me/partner/v1/customers/` — Customer creation (Partner)
- `api.pagar.me/lifecycle/v1/accounts/` — Account creation
- `api.pagar.me/lifecycle/v1/merchants/` — Merchant queries
- `api.pagar.me/core/v1/accounts/` — Account configuration

These are being replaced by [[payments-lifecycle]] as part of [[2026-04-feature-new-payments-modeling]].

## Possible Connections

- [[payments-lifecycle]] — Replacement platform
- [[2026-04-feature-new-payments-modeling]] — Context for deprecation

## Capture Context

Extracted from Confluence page "Introdução a Nova modelagem" in RCON space. Multiple distinct APIs grouped here because they don't map to a single actor — may need splitting into individual actors once repo names are confirmed.

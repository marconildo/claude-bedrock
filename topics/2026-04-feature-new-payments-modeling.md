---
type: topic
title: "New Payments Modeling"
aliases: ["Introdução a Nova Modelagem", "Nova Modelagem Payments", "New Payments Entity Model"]
category: "feature"
status: "in-progress"
people: []
actors: ["[[payments-lifecycle]]", "[[affiliation-service-layer]]", "[[mundipagg-lifecycle]]", "[[distribution]]", "[[identity]]"]
objective: "Unify the payment entity model across Stone, Ton, and Pagar.me brands into a single brand-agnostic platform"
created_at: 2026-04-14
sources:
  - url: "https://allstone.atlassian.net/wiki/spaces/RCON/pages/8283750802/Introdu+o+a+Nova+modelagem#PaymentProfile"
    type: "confluence"
    synced_at: 2026-04-14
updated_at: 2026-04-14
updated_by: "preserve@agent"
tags: [type/topic, status/in-progress, category/feature, domain/payments]
---

<!-- Zettelkasten role: bridge note -->
<!-- Links in the body explain WHY permanents relate -->

# New Payments Modeling

> Restructuring the Payments domain model to unify Stone, Ton, and Pagar.me into a single brand-agnostic platform, resolving historical problems of scope, coupling, and duplicated data.

## Context

The new Payments modeling was proposed to solve historical problems across the three brands:

- Entities without defined scope
- Data aggregation and tight coupling
- Low flexibility leading to data duplication
- Scattered responsibilities
- Being the customer base for some segments
- Long dependency chains for launching new products

The previous model had different entity structures per brand (Stone used Merchant/CaptureMethod with StoneCode, Ton used Merchant/Agreement/StoneMerchant/PagarmeMerchant with AgreementId, Pagar.me used Merchant/Account/Company/Recipient with AccountId and CompanyId).

## New Entity Hierarchy

The unified model introduces a single entity hierarchy for all brands:

- **Merchant** — 1:1 with a document (CNPJ/CPF). Groups PaymentProfiles and Agreements.
- **PaymentProfile** — Set of POIs and their configurations. Represents the client's sales operation.
- **POI (Point of Interaction)** — Transactional processing configurations per channel: pos, micropos, tef, taponphone, ecommerce, link, manualEntry. Carries settlement bank account data.
- **CaptureMethod** — Transaction capture method (e.g., terminal for card-present).
- **Agreement** — Commercial conditions (fees, RAV delay, contracted products). Can be scoped at PaymentProfile, Merchant, or plan level.
- **Recipient** — Marketplace seller entity with own registration, settlement, and commercial conditions.

New identifiers: MerchantId, AgreementId, PaymentProfileId, PoiId, CaptureMethodId, RecipientId.

## Key Mappings (Legacy → New)

- **StoneCode** → 1 POI (StoneCode descends in hierarchy, becomes a POI identifier)
- **CaptureMethod (Stone)** → 1 POI type
- **Terminal** → 1 CaptureMethod
- **Merchant (Ton)** → 1 Merchant (same grouping concept, reused)
- **Agreement (Ton)** → N Agreements (removes limitation of one per capture method)
- **Account (Pagar.me)** → 1 PaymentProfile
- **Company (Pagar.me)** → Discontinued
- **Recipient (Pagar.me)** → 1 Recipient (DefaultRecipient data incorporated into PaymentProfile)

## Retrocompatibility

Legacy identifiers (StoneCode, SAK, accounts, Pagar.me merchants) continue to be created and are stored in a **Legacy Identifiers** relational table. This enables bidirectional lookup between old and new identifiers via [[payments-lifecycle]] API routes like `/v2/legacy-identifiers/filter`.

## Actors Involved

| Actor | Relation |
|---|---|
| [[payments-lifecycle]] | New unified platform — `api.stone.com.br/payments-lifecycle/v2/` |
| [[affiliation-service-layer]] | Legacy Stone service being replaced |
| [[mundipagg-lifecycle]] | Legacy Ton service being replaced |
| [[distribution]] | Commercial conditions management (ActiveOffer) |
| [[identity]] | Cadastral data management (StoneAccount, Legal Entity) |

## Decisions

- Brand-agnostic platform: the new model is the same for Stone, Ton, and Pagar.me — teams can operate the payment product without systemic locks
- Decoupling from Payments base: the client experience is no longer conditioned by the payment platform's structure
- Retrocompatibility via Legacy Identifiers: ensures smooth migration and ability to float clients between old and new structures
- Agreement granularity: pricing can be defined per POI type within an Agreement, enabling fine-grained commercial conditions

## Next Steps

- [ ] Route and contract definition (expected by end of Q3)
- [ ] Third-party teams mapping of critical routes per operation
- [ ] Migration of existing clients to new structure

## History

| Date | Event |
|---|---|
| 2026-04-14 | Confluence page ingested via /bedrock:teach |

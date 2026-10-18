---
schema: aether.architecture-document/v1
id: store-decisions
title: Ego Hygiene Store Decisions
kind: architecture-document
version: 0.3.0
status: provisional
owners:
  - egohygiene
created: 2026-08-19
updated: 2026-10-17
governed_by:
  - architecture-decisions
depends_on:
  - store-principles
  - store-epistemology
  - store-foundations
  - store-system
  - store-architecture
related:
  - store-purpose
  - store-vision
  - store-pillars
  - store-manifesto
supersedes: []
---

# Ego Hygiene Store Decisions

## Purpose

This document preserves significant accepted architectural choices and their rationale. Issues coordinate work, proposals explore alternatives, and this file records decisions that constrain future implementation.

## Governance

Do not rewrite historical context to fit current understanding. Amend a record for corrections that do not change meaning; supersede it with a new record when the decision changes materially.

## Index

- ADR-0001: Normalize providers behind a commerce port
- ADR-0002: Use hosted checkout
- ADR-0003: Deploy independently beneath the /store route
- ADR-0004: Preserve the community-store direction and reconcile deployment ownership
- ADR-0005: Select the website as the V1 storefront owner (proposed for review)

## ADR-0001: Normalize providers behind a commerce port

- **Status:** Accepted as the current architectural direction
- **Date:** 2026-08-19
- **Context:** Repository evidence and ecosystem ownership require an explicit durable boundary.
- **Decision:** Normalize providers behind a commerce port.
- **Consequences:** The choice improves ownership and predictability while requiring maintained contracts, validation, and migration discipline.
- **Reconsider when:** New evidence shows that the boundary prevents standalone usefulness, safety, portability, or maintainability.

## ADR-0002: Use hosted checkout

- **Status:** Accepted as the current architectural direction
- **Date:** 2026-08-19
- **Context:** Repository evidence and ecosystem ownership require an explicit durable boundary.
- **Decision:** Use hosted checkout.
- **Consequences:** The choice improves ownership and predictability while requiring maintained contracts, validation, and migration discipline.
- **Reconsider when:** New evidence shows that the boundary prevents standalone usefulness, safety, portability, or maintainability.

## ADR-0003: Deploy independently beneath the /store route

- **Status:** Accepted as the current architectural direction
- **Date:** 2026-08-19
- **Context:** Repository evidence and ecosystem ownership require an explicit durable boundary.
- **Decision:** Deploy independently beneath the /store route.
- **Consequences:** The choice improves ownership and predictability while requiring maintained contracts, validation, and migration discipline.
- **Reconsider when:** New evidence shows that the boundary prevents standalone usefulness, safety, portability, or maintainability.

### Review note for ADR-0003, 2026-10-16

The original record above is preserved. The website repository's
[high-level ADR-0004](https://github.com/egohygiene/egohygiene.io/blob/db634b887ede348ce85d9c03af789467ab535dcf/DECISIONS.md#adr-0004-consolidate-the-store-v1-website-and-use-hosted-checkout)
instead places the canonical storefront in `apps/egohygiene.io`. Both
repositories contain store implementations. This conflict must be reconciled;
neither decision is silently superseded by the current discussion. Independent
path routing and a composed build remain options, not approved topology.

The subsequent [ADR-0005](#adr-0005-select-the-website-as-the-v1-storefront-owner)
selects a successor direction for review. This October 16 note remains the
historical conflict record, not the current work queue.

## ADR-0004: Preserve the community-store direction and reconcile deployment ownership

- **Status:** Accepted product goals and development-preview preference;
  canonical store ownership, deployment topology, and production host unresolved.
- **Date:** 2026-10-16.
- **Context:** The user wants the root site to explain Ego Hygiene and grow into
  its core product. The store supports the community. Phone-based development
  needs a hosted preview without a running laptop. Existing repositories record
  conflicting store ownership and deployment directions.
- **Decision:** Preserve `/store` under the main domain, feature `.play()` as an
  artist, and separate the large song-merch catalog from curated standalone
  designs. Prefer a reusable GitHub Actions workflow that updates a Netlify
  development preview after integration into `development`. Compare both store
  implementations and name one canonical owner before implementing deployment.
  Retain separate provider checkout flows for V1. Fourthwall is the first merch
  candidate; comics and Alpal begin with honest development placeholders.
- **Consequences:** Public URL structure does not force repository consolidation
  or independent hosting. Google versus Cloudflare production hosting remains
  open. Accounts, Kubernetes, and a universal cart are not V1 prerequisites.
  Private creative sources stay outside public website input; only approved
  public derivatives and metadata cross that boundary.
- **Scope:** Captures discussion; does not activate infrastructure, change branch
  protection, qualify providers, create issues, transfer repositories, or assert
  successful purchases. Milestones and parent/child issues are proposals pending
  user review. Keeping `incomprisllc/merch` in its current private home is a
  recommendation; no transfer decision has been made.
- **Evidence:** [Dated checkpoint](docs/context/2026-10-16-store-launch-discussion.md)
  and [canonical launch-plan draft](https://github.com/egohygiene/egohygiene.io/blob/docs/store-launch-direction-20261016/docs/architecture/store-launch-plan.md).
- **Supersedes:** None. Reconcile ADR-0003 and the website's high-level ADR-0004
  explicitly after the implementation comparison.
- **Reconsider when:** The user approves canonical ownership, topology, or a
  production host, or provider evidence changes a proposed purchase flow.

## ADR-0005: Select the website as the V1 storefront owner

- **Status:** Proposed for review in paired ownership PRs. The comparison is
  complete; deployment and source migration have not occurred.
- **Date:** 2026-10-17 UTC.
- **Issue:** [Website #75](https://github.com/egohygiene/egohygiene.io/issues/75).
- **Context:** Both repositories contain real React/Vite storefronts. The
  website already preserves stable design, product, and collection routes, an
  approved public catalog projection, portable domain logic, and the broader
  Ego Hygiene site. This repository has useful commerce and cart code, but
  lacks equivalent catalog publication boundaries and live-provider evidence.
- **Selected direction:** Make `egohygiene/egohygiene.io` the canonical V1
  customer-facing app and compose one site build. Keep `egohygiene/store` as a
  preserved commerce reference and research source. Reuse useful capabilities
  selectively through the website's contracts after qualification. Keep
  provider-hosted checkout and separate provider flows.
- **Preservation:** Retain this repository, source history, mock environment,
  commerce ports, tests, existing issues, and MIT notice. Do not archive,
  transfer, delete, copy an entire app, or migrate private creative repositories
  as part of this decision. Any substantial copied code must retain its license
  notice and record its immutable source revision and destination.
- **Qualification:** The Fourthwall adapter has no adapter-specific tests at
  the inspected revision. Mock unit coverage and the single cart E2E do not
  prove hosted checkout, successful payment, or fulfillment. Reuse must address
  cart persistence/error/concurrency behavior, modal accessibility, provider
  response validation, and current provider contracts before live activation.
- **Consequences:** The website owns one deployment coordinator. Existing Vercel
  and prefix-stripping examples here are historical reference, not instructions
  to deploy a second store. Netlify preview work remains under website #29;
  Google versus Cloudflare production hosting remains open.
- **Supersession on acceptance:** Replace ADR-0003's independent V1 deployment
  direction and resolve the ownership/topology questions in ADR-0004. Preserve
  those records and their product goals. ADR-0001 and ADR-0002 remain applicable.
- **Evidence and counterpart:** [Ownership comparison](https://github.com/egohygiene/egohygiene.io/blob/docs/storefront-ownership-75/docs/architecture/storefront-ownership.md),
  [website ADR 0007](https://github.com/egohygiene/egohygiene.io/blob/docs/storefront-ownership-75/docs/architecture/decisions/0007-canonical-storefront-owner.md),
  and [dated receipt](docs/context/2026-10-17-storefront-ownership.md).
- **Reconsider when:** A qualified requirement needs independent release,
  hosting, or security boundaries strongly enough to justify a second app;
  document its contract and cutover plan before changing topology.

## Open decisions

- Acceptance of ADR-0005 and its preservation plan in the paired ownership PRs.
- Which commerce capabilities to reuse after qualification, and their destination contracts.
- Production hosting and the exact implementation of the development-preview workflow.
- Release and compatibility policy for the first stable version.
- Exact self-hosted, managed, and organization-integrated deployment boundaries.
- Which target systems must exist before the architecture status may become active.

## Evidence and uncertainty

- **Observed:** The repository README establishes the intended boundary as a provider-neutral React and Vite storefront for the egohygiene.io store experience; significant implementation remains incomplete.
- **Decided for this draft:** The repository owns the bounded concern described here and participates through versioned contracts.
- **Proposed:** Target systems and later roadmap phases remain proposals until accepted and implemented.
- **Open question:** Which parts of this draft should become active in the first independently versioned release?

## Identifier format migration (2026-10-18)

The maintainer selected four-digit numbering in [Hygiene #73](https://github.com/egohygiene/hygiene/issues/73). This padding-only migration changes current labels and anchors; logical numbers, decision content, dates and disposition remain unchanged. Git retains prior versions. New canonical records use `ADR-NNNN` under Hygiene policy v1.2.0.

| Previous ID | Current ID | Record |
| --- | --- | --- |
| `ADR-001` | `ADR-0001` | [DECISIONS.md](DECISIONS.md#adr-0001-normalize-providers-behind-a-commerce-port) |
| `ADR-002` | `ADR-0002` | [DECISIONS.md](DECISIONS.md#adr-0002-use-hosted-checkout) |
| `ADR-003` | `ADR-0003` | [DECISIONS.md](DECISIONS.md#adr-0003-deploy-independently-beneath-the-store-route) |
| `ADR-004` | `ADR-0004` | [DECISIONS.md](DECISIONS.md#adr-0004-preserve-the-community-store-direction-and-reconcile-deployment-ownership) |
| `ADR-005` | `ADR-0005` | [DECISIONS.md](DECISIONS.md#adr-0005-select-the-website-as-the-v1-storefront-owner) |

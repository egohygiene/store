---
schema: aether.architecture-document/v1
id: store-decisions
title: Ego Hygiene Store Decisions
kind: architecture-document
version: 0.2.0
status: provisional
owners:
  - egohygiene
created: 2026-08-19
updated: 2026-10-16
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

- ADR-001: Normalize providers behind a commerce port
- ADR-002: Use hosted checkout
- ADR-003: Deploy independently beneath the /store route
- ADR-004: Preserve the community-store direction and reconcile deployment ownership

## ADR-001: Normalize providers behind a commerce port

- **Status:** Accepted as the current architectural direction
- **Date:** 2026-08-19
- **Context:** Repository evidence and ecosystem ownership require an explicit durable boundary.
- **Decision:** Normalize providers behind a commerce port.
- **Consequences:** The choice improves ownership and predictability while requiring maintained contracts, validation, and migration discipline.
- **Reconsider when:** New evidence shows that the boundary prevents standalone usefulness, safety, portability, or maintainability.

## ADR-002: Use hosted checkout

- **Status:** Accepted as the current architectural direction
- **Date:** 2026-08-19
- **Context:** Repository evidence and ecosystem ownership require an explicit durable boundary.
- **Decision:** Use hosted checkout.
- **Consequences:** The choice improves ownership and predictability while requiring maintained contracts, validation, and migration discipline.
- **Reconsider when:** New evidence shows that the boundary prevents standalone usefulness, safety, portability, or maintainability.

## ADR-003: Deploy independently beneath the /store route

- **Status:** Accepted as the current architectural direction
- **Date:** 2026-08-19
- **Context:** Repository evidence and ecosystem ownership require an explicit durable boundary.
- **Decision:** Deploy independently beneath the /store route.
- **Consequences:** The choice improves ownership and predictability while requiring maintained contracts, validation, and migration discipline.
- **Reconsider when:** New evidence shows that the boundary prevents standalone usefulness, safety, portability, or maintainability.

### Review note for ADR-003, 2026-10-16

The original record above is preserved. The website repository's
[high-level ADR-004](https://github.com/egohygiene/egohygiene.io/blob/db634b887ede348ce85d9c03af789467ab535dcf/DECISIONS.md#adr-004-consolidate-the-store-v1-website-and-use-hosted-checkout)
instead places the canonical storefront in `apps/egohygiene.io`. Both
repositories contain store implementations. This conflict must be reconciled;
neither decision is silently superseded by the current discussion. Independent
path routing and a composed build remain options, not approved topology.

## ADR-004: Preserve the community-store direction and reconcile deployment ownership

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
- **Supersedes:** None. Reconcile ADR-003 and the website's high-level ADR-004
  explicitly after the implementation comparison.
- **Reconsider when:** The user approves canonical ownership, topology, or a
  production host, or provider evidence changes a proposed purchase flow.

## Open decisions

- Canonical store owner and migration/preservation plan across both actual implementations.
- Composed build versus independent deployments with path routing.
- Production hosting and the exact implementation of the development-preview workflow.
- Release and compatibility policy for the first stable version.
- Exact self-hosted, managed, and organization-integrated deployment boundaries.
- Which target systems must exist before the architecture status may become active.

## Evidence and uncertainty

- **Observed:** The repository README establishes the intended boundary as a provider-neutral React and Vite storefront for the egohygiene.io store experience; significant implementation remains incomplete.
- **Decided for this draft:** The repository owns the bounded concern described here and participates through versioned contracts.
- **Proposed:** Target systems and later roadmap phases remain proposals until accepted and implemented.
- **Open question:** Which parts of this draft should become active in the first independently versioned release?


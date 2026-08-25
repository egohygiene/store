---
schema: aether.architecture-document/v1
id: store-roadmap
title: Ego Hygiene Store Roadmap
kind: architecture-document
version: 0.1.0
status: provisional
owners:
  - egohygiene
created: 2026-08-19
updated: 2026-08-24
governed_by:
  - architecture-roadmap
depends_on:
  - store-vision
  - store-pillars
  - store-architecture
  - store-decisions
related:
  - store-purpose
  - store-principles
  - store-manifesto
  - store-epistemology
supersedes: []
---

# Ego Hygiene Store Roadmap

<!-- BEGIN ROADMAP EXECUTION SNAPSHOT -->
<!-- roadmap-manifest
schema: hygiene.roadmap/v1alpha1
repository: egohygiene/store
visibility: public
publication: central
route: /roadmap/store/
updated: 2026-08-24
-->
## 2026-08-24 execution snapshot

> This evidence-reconciled snapshot is the issue-generation and visual-roadmap handoff. The longer-horizon strategy below remains canonical context; generated HTML, JSON, progress, issue plans, and commit lists are projections.

**Lifecycle:** mock-commerce alpha  
**Current gate:** Fix the duplicate Black/Small E2E locator and obtain a green replacement for red PR #10 before claiming deploy readiness.  
**North-star outcome:** A portable live storefront at /store with provider-neutral commerce boundaries and verified fulfillment paths.

### Visual roadmap publication

**Mode:** `central`  
**Route:** `/roadmap/store/`  
**Current publication evidence:** Web storefront target at /store; no production deployment was proven.

Publish the public-safe projection through egohygiene.io at /roadmap/store/. This repository owns intent and acceptance evidence; it does not add a second site deployment.

### Quest line

<!-- roadmap-step
id: STO-Q01
status: complete
depends_on: []
issues: []
-->
#### STO-Q01 — Build the storefront alpha

**State:** `complete`  
**Depends on:** None

**Outcome:** A mock-commerce storefront and baseline quality checks exist.

**Exit criteria:**

- [x] The main user interface and mock catalog flow are implemented.
- [x] Static quality checks pass.

**Current evidence:**

- The audit observed a functional mock-commerce alpha with green quality checks.

<!-- roadmap-step
id: STO-Q02
status: blocked
depends_on: [STO-Q01]
issues: []
-->
#### STO-Q02 — Recover end-to-end confidence

**State:** `blocked`  
**Depends on:** `STO-Q01`

**Outcome:** The storefront purchase-path tests are deterministic and green.

**Exit criteria:**

- [ ] The Black/Small selector resolves one intended element.
- [ ] PR #10 or a superseding change passes the full E2E workflow.

**Current evidence:**

- E2E failed on a duplicate Black/Small locator.
- PR #10 was red.

<!-- roadmap-step
id: STO-Q03
status: planned
depends_on: [STO-Q02]
issues: []
-->
#### STO-Q03 — Connect and verify live commerce

**State:** `planned`  
**Depends on:** `STO-Q02`

**Outcome:** A real Fourthwall-backed purchase path works in a safe test or production environment.

**Exit criteria:**

- [ ] Catalog, variant, cart, and handoff behavior use live provider data.
- [ ] A documented test order or provider-approved equivalent proves the path.

**Current evidence:**

- No live commerce proof was observed.

<!-- roadmap-step
id: STO-Q04
status: planned
depends_on: [STO-Q02, STO-Q03]
issues: []
-->
#### STO-Q04 — Deploy and prove /store

**State:** `planned`  
**Depends on:** `STO-Q02`, `STO-Q03`

**Outcome:** The storefront is available under the intended stable route with monitored deploy evidence.

**Exit criteria:**

- [ ] A green workflow publishes /store.
- [ ] Deep links, assets, and checkout handoff work at the deployed base path.

**Current evidence:**

- No proven deployment was observed.

<!-- roadmap-step
id: STO-Q05
status: planned
depends_on: [STO-Q04]
issues: [9, 11, 13]
-->
#### STO-Q05 — Harden provider boundaries and consolidate the roadmap

**State:** `planned`  
**Depends on:** `STO-Q04`

**Outcome:** Issues #9, #11, #12, and #13 advance on one authoritative roadmap without binding the UI to one vendor.

**Exit criteria:**

- [ ] Issue #11 yields a tested provider interface.
- [ ] Root and docs roadmaps are reconciled into one source of truth.

**Current evidence:**

- Issues #9 and #11-#13 form the identified backlog.
- Root and docs roadmaps currently conflict.

### Roadmap-to-issue handoff

- A step is complete only when its exit criteria and required evidence are satisfied; commit count never determines progress.
- Ready steps without an issue are candidates for the private, duplicate-aware roadmap.issue-plan.json dry run. Planned steps remain preview-only unless a reviewer explicitly opts them in with issue_policy: propose.
- Issue creation or reconciliation requires human approval or an explicitly authorized Pace operation and returns issue references through a reviewable roadmap pull request.
- Pull requests and commits should include Roadmap-Step: <ID>; historical evidence may be linked through existing issue and pull-request relationships.
- Public rendering uses only allowlisted build-time evidence and never places a GitHub token or private issue plan in the browser artifact.

<!-- END ROADMAP EXECUTION SNAPSHOT -->

## Strategic context

This roadmap describes capability evolution, not promised dates or an issue queue. Sequence follows architecture dependencies and may change when evidence or risk changes.

## Phase 1: Harden mock and provider ports

**Outcome:** A bounded capability advances from documented intent to validated, independently usable behavior.

**Exit signals:**

- The owning contract and acceptance criteria are versioned.
- Implementation and documentation agree.
- Relevant tests and safety checks pass.
- Downstream consumers and migration impact are understood.
- Remaining uncertainty is visible.

## Phase 2: Complete production Fourthwall setup

**Outcome:** A bounded capability advances from documented intent to validated, independently usable behavior.

**Exit signals:**

- The owning contract and acceptance criteria are versioned.
- Implementation and documentation agree.
- Relevant tests and safety checks pass.
- Downstream consumers and migration impact are understood.
- Remaining uncertainty is visible.

## Phase 3: Add observability and accessibility evidence

**Outcome:** A bounded capability advances from documented intent to validated, independently usable behavior.

**Exit signals:**

- The owning contract and acceptance criteria are versioned.
- Implementation and documentation agree.
- Relevant tests and safety checks pass.
- Downstream consumers and migration impact are understood.
- Remaining uncertainty is visible.

## Phase 4: Evaluate accounts and order history

**Outcome:** A bounded capability advances from documented intent to validated, independently usable behavior.

**Exit signals:**

- The owning contract and acceptance criteria are versioned.
- Implementation and documentation agree.
- Relevant tests and safety checks pass.
- Downstream consumers and migration impact are understood.
- Remaining uncertainty is visible.

## Phase 5: Support additional providers if justified

**Outcome:** A bounded capability advances from documented intent to validated, independently usable behavior.

**Exit signals:**

- The owning contract and acceptance criteria are versioned.
- Implementation and documentation agree.
- Relevant tests and safety checks pass.
- Downstream consumers and migration impact are understood.
- Remaining uncertainty is visible.

## Cross-cutting tracks

- Security, privacy, accessibility, licensing, and provenance.
- Documentation, architecture portals, examples, and onboarding.
- Packaging, release, compatibility, and self-hosting.
- Organization integration through explicit contracts.
- Observatory evidence and Pace conformance when those systems exist.

## Deferred direction

Optional managed services, enterprise controls, marketplaces, and the conversational organization compiler remain later architecture work. Current choices should preserve portability and avoid foreclosing them.

## Evidence and uncertainty

- **Observed:** The repository README establishes the intended boundary as a provider-neutral React and Vite storefront for the egohygiene.io store experience; significant implementation remains incomplete.
- **Decided for this draft:** The repository owns the bounded concern described here and participates through versioned contracts.
- **Proposed:** Target systems and later roadmap phases remain proposals until accepted and implemented.
- **Open question:** Which parts of this draft should become active in the first independently versioned release?

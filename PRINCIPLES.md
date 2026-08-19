---
schema: aether.architecture-document/v1
id: store-principles
title: Ego Hygiene Store Principles
kind: architecture-document
version: 0.1.0
status: provisional
owners:
  - egohygiene
created: 2026-08-19
updated: 2026-08-19
governed_by:
  - architecture-principles
depends_on:
  - store-purpose
  - store-vision
related:
  - store-pillars
  - store-manifesto
  - store-epistemology
  - store-ai-constitution
supersedes: []
---

# Ego Hygiene Store Principles

## Purpose

These principles guide decisions when multiple valid options exist. They do not replace policy, accepted decisions, specifications, or implementation standards.

## 1. Provider details stay behind ports

**Guidance:** Prefer choices that make this principle observable in contracts, behavior, and evidence.

**Trade-off:** Accept some additional explicitness and validation when it prevents hidden coupling, lost provenance, or irreversible surprise.

## 2. Mock mode remains first-class

**Guidance:** Prefer choices that make this principle observable in contracts, behavior, and evidence.

**Trade-off:** Accept some additional explicitness and validation when it prevents hidden coupling, lost provenance, or irreversible surprise.

## 3. Checkout authority stays explicit

**Guidance:** Prefer choices that make this principle observable in contracts, behavior, and evidence.

**Trade-off:** Accept some additional explicitness and validation when it prevents hidden coupling, lost provenance, or irreversible surprise.

## 4. Accessibility precedes conversion

**Guidance:** Prefer choices that make this principle observable in contracts, behavior, and evidence.

**Trade-off:** Accept some additional explicitness and validation when it prevents hidden coupling, lost provenance, or irreversible surprise.

## 5. Secrets never enter the browser bundle

**Guidance:** Prefer choices that make this principle observable in contracts, behavior, and evidence.

**Trade-off:** Accept some additional explicitness and validation when it prevents hidden coupling, lost provenance, or irreversible surprise.

## Precedence and exceptions

Safety, human agency, privacy, and explicit policy take precedence over convenience and speed. Exceptions require a recorded rationale, bounded duration when temporary, validation evidence, and a review trigger.

## Evidence and uncertainty

- **Observed:** The repository README establishes the intended boundary as a provider-neutral React and Vite storefront for the egohygiene.io store experience; significant implementation remains incomplete.
- **Decided for this draft:** The repository owns the bounded concern described here and participates through versioned contracts.
- **Proposed:** Target systems and later roadmap phases remain proposals until accepted and implemented.
- **Open question:** Which parts of this draft should become active in the first independently versioned release?

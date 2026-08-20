---
schema: aether.architecture-document/v1
id: store-ontology
title: Ego Hygiene Store Ontology
kind: architecture-document
version: 0.1.0
status: provisional
owners:
  - egohygiene
created: 2026-08-19
updated: 2026-08-19
governed_by:
  - architecture-ontology
depends_on:
  - store-purpose
  - store-vision
  - store-principles
  - store-epistemology
related:
  - store-pillars
  - store-manifesto
  - store-ai-constitution
  - store-personal-model
supersedes: []
---

# Ego Hygiene Store Ontology

## Domain scope

Ego Hygiene Store models the concepts needed for offer sustainable products and artifacts through an accessible storefront without coupling the user experience to one commerce provider. The ontology names conceptual entities and relationships; it is not a source-code class model, API schema, or database design.

## Canonical concepts

| Concept | Meaning |
| --- | --- |
| Product | A canonical concept in the Ego Hygiene Store domain whose exact fields belong to specifications or schemas, not this ontology. |
| Collection | A canonical concept in the Ego Hygiene Store domain whose exact fields belong to specifications or schemas, not this ontology. |
| Variant | A canonical concept in the Ego Hygiene Store domain whose exact fields belong to specifications or schemas, not this ontology. |
| Cart | A canonical concept in the Ego Hygiene Store domain whose exact fields belong to specifications or schemas, not this ontology. |
| Cart line | A canonical concept in the Ego Hygiene Store domain whose exact fields belong to specifications or schemas, not this ontology. |
| Checkout | A canonical concept in the Ego Hygiene Store domain whose exact fields belong to specifications or schemas, not this ontology. |
| Commerce provider | A canonical concept in the Ego Hygiene Store domain whose exact fields belong to specifications or schemas, not this ontology. |
| Adapter | A canonical concept in the Ego Hygiene Store domain whose exact fields belong to specifications or schemas, not this ontology. |
| Customer | A canonical concept in the Ego Hygiene Store domain whose exact fields belong to specifications or schemas, not this ontology. |
| Fulfillment | A canonical concept in the Ego Hygiene Store domain whose exact fields belong to specifications or schemas, not this ontology. |

## Core relationships

- A repository or person provides source context to one or more domain artifacts.
- A specification constrains how an artifact is interpreted or produced.
- A plan separates proposed action from execution.
- Evidence supports a claim; a decision authorizes a durable direction.
- Provenance connects derived artifacts to their inputs and processing context.
- A consumer integrates through an explicit interface rather than internal structure.

## Boundaries

- Conceptual identity is distinct from filesystem path, database identifier, or display label.
- Observed state is distinct from desired state.
- Proposed relationships are not accepted facts.
- Neighboring repositories retain ownership of their domain concepts.

## Evidence and uncertainty

- **Observed:** The repository README establishes the intended boundary as a provider-neutral React and Vite storefront for the egohygiene.io store experience; significant implementation remains incomplete.
- **Decided for this draft:** The repository owns the bounded concern described here and participates through versioned contracts.
- **Proposed:** Target systems and later roadmap phases remain proposals until accepted and implemented.
- **Open question:** Which parts of this draft should become active in the first independently versioned release?

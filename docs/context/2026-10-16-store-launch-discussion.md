# Store launch discussion checkpoint

- **ID:** `cp-20261016-store-launch-direction`.
- **Date:** 2026-10-16, America/New_York.
- **Source:** User/assistant store architecture discussion and the repository
  revisions below. This is a curated checkpoint, not a complete transcript.
- **Authority:** Capture context and decisions in the website and store
  repositories for review. New issues require the user's next approval.
- **Canonical plan:** [Website launch-plan draft](https://github.com/egohygiene/egohygiene.io/blob/docs/store-launch-direction-20261016/docs/architecture/store-launch-plan.md).

## Why this direction

The user wants a real store that can launch with minimal ongoing cost and also
serve as a production engineering learning project. Work should advance in
small reviewable steps. The root site explains Ego Hygiene and eventually hosts
its core product; commerce supports the community rather than replacing that
identity. Existing repository documentation subdomains can stay separate.

The user wants to commit freely from a phone, then review a remotely hosted
update after a merge without keeping a laptop running. The preferred path is a
`development` integration branch, a reusable GitHub Actions workflow, and a
stable Netlify development-preview URL. A branch update is the actual trigger;
merge-only behavior needs PR-based branch policy. Avoid duplicate Netlify Git
builds if Actions owns deployment. Exact setup, limits, and permissions must be
verified during implementation; this checkpoint does not promise unlimited
free usage or choose the production host.

## Product direction to retain

- `/` presents Ego Hygiene's mission and future product. `/store` serves
  community merchandise, including Ego Hygiene designs and featured artists.
- `.play()` is a featured artist for now. Curated standalone work should remain
  visible without being flooded by the roughly 400-song merch catalog. Songs
  need stable public destinations so SoundCloud links can survive provider
  changes. Exact additional routes remain design work.
- Designs, products/variants, artist attribution, collection membership, song
  associations, and fulfillment providers are distinct relationships. One
  design may support several products; song associations may be empty.
- Start with merchandise that can be purchased through a qualified provider.
  Fourthwall is the first candidate. Use separate provider checkout flows;
  a cross-provider cart is outside the first release.
- Comics and Alpal initially receive honest development pages. Lulu is a comic
  candidate and Makeship a campaign candidate, subject to qualification. A later
  milestone is buying the first comic through the store and receiving it.
- Accounts, Kubernetes, custom load balancing, and a production platform
  migration are not prerequisites for the first useful storefront. Keep build
  and domain logic portable while choosing infrastructure only as needed.

## Newly observed ownership conflict

| Source | Observed direction |
| --- | --- |
| [Store main](https://github.com/egohygiene/store/tree/599c90ca6a454c0f2e9aa95eab5f8395016474c5) | React/Vite storefront, commerce port, mock/Fourthwall adapters, cart operations, and independent `/store/` deployment configuration |
| [Website main](https://github.com/egohygiene/egohygiene.io/tree/db634b887ede348ce85d9c03af789467ab535dcf) | Website with implemented store feature, public catalog contracts, portable domain, and synthetic provider-preview boundary |
| Store [ADR-003](../../DECISIONS.md#adr-003-deploy-independently-beneath-the-store-route) | Independent store deployment under `/store` |
| Website [high-level ADR-004](https://github.com/egohygiene/egohygiene.io/blob/db634b887ede348ce85d9c03af789467ab535dcf/DECISIONS.md#adr-004-consolidate-the-store-v1-website-and-use-hosted-checkout) | Canonical store inside the website application |

Both stores are real implementations. Their relative completeness and verified
behavior have not been resolved by this documentation task. Compare them before
selecting the canonical owner; preserve useful work and provenance explicitly.
One assembled site build and independently deployed apps behind path routing
are alternatives. A shared URL alone does not decide between them. Two workflows
must not upload competing partial builds to the same deployment destination.

## Private sources and organization

The recommendation is to keep `incomprisllc/merch` as the private creative source
and publish only approved catalog records and optimized display derivatives to
the public site. Keep ownership/attribution separate from the hosting
organization and fulfillment provider. Moving a repository to `egohygiene` is
not required for a unified site and has not been authorized by this checkpoint.
Customer records, secrets, and unpublished masters do not belong in public Git
history. The private music catalog can retain richer source metadata without
making the browser depend on a private repository.

## Pending review and evidence

The next step is review of the
[milestone/parent-issue/sub-issue proposal](https://github.com/egohygiene/egohygiene.io/blob/docs/store-launch-direction-20261016/docs/roadmaps/store-launch.md).
Only after approval should missing issues be created or existing relationships
reorganized, followed by another sync. Implementation begins with ownership
reconciliation when authorized. No issues have been created by this capture.
Do not start infrastructure or supplier activation from this record.
Provider APIs, eligibility, fees, and hosting limits require dated primary
evidence when their implementation checkpoint begins; the website plan owns
the research references rather than duplicating mutable pricing here.

This note records source inspection and user preferences. It claims no fresh
application test results, production deployment, provider qualification, or
physical fulfillment. Add later checkpoints with exact revisions and actual
results; preserve this note as the discussion history.

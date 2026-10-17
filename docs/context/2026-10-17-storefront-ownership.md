# Storefront ownership checkpoint

- **ID:** `cp-20261017-storefront-ownership`.
- **Date:** 2026-10-17 UTC, following the user's October 16 evening instruction.
- **Authority:** Merge the planning PRs, then undertake the first bounded issue
  before the next sync. The broader proposed backlog remains unapproved.
- **Issue:** [Website #75](https://github.com/egohygiene/egohygiene.io/issues/75).
- **Review branch:** `docs/storefront-ownership-75` in both repositories.
- **Status:** Comparison and selected direction prepared for paired draft review;
  ownership acceptance and deployment remain separate checkpoints.

## Merge and source receipts

| Evidence | Revision |
| --- | --- |
| [Store planning PR #33](https://github.com/egohygiene/store/pull/33) merged | `bfda1a7c6b0ce09258522be8d8fe4bf9cba8b5a3` |
| [Website planning PR #74](https://github.com/egohygiene/egohygiene.io/pull/74) merged | `ee59e2f83c59c084c23a5f8bcc3311c2dc830859` |
| [Store implementation audited](https://github.com/egohygiene/store/tree/599c90ca6a454c0f2e9aa95eab5f8395016474c5) | `599c90ca6a454c0f2e9aa95eab5f8395016474c5` |
| [Website implementation audited](https://github.com/egohygiene/egohygiene.io/tree/db634b887ede348ce85d9c03af789467ab535dcf) | `db634b887ede348ce85d9c03af789467ab535dcf` |

Planning changes are documentation only. Existing application/check failures
are separate evidence and are not resolved by these merge receipts.

## Finding and selected direction

Both repositories contain real stores. The website already carries the public
catalog projection, stable design/product/collection paths, and broader site
identity. This repository contributes working source structures for normalized
commerce operations, mock carts, Fourthwall requests, browser cart IDs, and
hosted-checkout handoff. Its existence does not justify a second canonical app.

Select the website app and one composed V1 build. Keep this repository available
as a commerce reference and provider-research source. Preserve code and history
while adapting qualified capabilities selectively. The full
[comparison and cutover plan](https://github.com/egohygiene/egohygiene.io/blob/docs/storefront-ownership-75/docs/architecture/storefront-ownership.md)
and [website ADR 0007](https://github.com/egohygiene/egohygiene.io/blob/docs/storefront-ownership-75/docs/architecture/decisions/0007-canonical-storefront-owner.md)
own the cross-repository detail; [store ADR-005](../../DECISIONS.md#adr-005-select-the-website-as-the-v1-storefront-owner)
records the local successor proposal. Draft branch links must be refreshed after
merge; they are not immutable release evidence.

## Preservation inventory and observed gaps

| Source | Preserve or qualify |
| --- | --- |
| `packages/commerce/src/types.ts` | Normalized client/operation concepts; reconcile with website catalog and purchase states |
| `packages/commerce/src/fourthwall/fourthwall-client.ts` | Request/normalization reference; qualify current provider contracts and add adapter evidence before reuse |
| `packages/commerce/src/mock/` | Credential-free examples and cart fixtures; current cart contents are in memory |
| `packages/store-config/src/index.ts` | Explicit mock/Fourthwall configuration and public Storefront-token distinction |
| `apps/storefront/src/features/storefront/` | Browser cart lifecycle reference; global cart-ID key needs provider/shop scoping and error/concurrency review |
| `apps/storefront/src/components/CartDrawer.tsx` | Cart interaction reference; mutation feedback and modal focus behavior need qualification |
| `tests/e2e/storefront.spec.ts` | One add-to-cart journey; ambiguous text locator and no hosted-checkout assertion |
| `LICENSE` | Complete MIT notice, copyright Ego Hygiene 2026; retain on substantial code reuse |
| `vercel.json`, `docs/domain-routing.md` | Historical independent-host routing evidence; do not apply to the composed V1 build |

The inspected test inventory has five unit cases (mock cart, configuration,
money formatting) and one browser journey. No Fourthwall adapter-specific test
was found. The provider money mapper accepts strings via `Number()` without
finite-value validation; stock availability uses string heuristics. These are
qualification findings, not newly reproduced runtime failures. Local source
inspection does not prove a live shop, completed payment, or physical delivery.

The website's license file/declaration mismatch is a separate gate before
substantial code reuse. No license is inferred or rewritten here. No private
creative records or customer data were imported.

## Continuation

Review the paired draft PRs in the next sync, then record acceptance explicitly.
Website #29 remains the CI/preview owner; store #32 remains the existing
cart/handoff evidence owner. Keep the rest of the proposed milestone hierarchy
for review rather than generating duplicate issues overnight. No provider,
deployment, archive, repository transfer, or purchase was performed.

Documentation checks cover relative link targets against the repository tree,
available anchors, fence balance, whitespace, and final newlines. Application
tests were not rerun for this documentation-only ownership checkpoint.

## Publication and verification receipt

[Store draft PR #34](https://github.com/egohygiene/store/pull/34) and
[website draft PR #76](https://github.com/egohygiene/egohygiene.io/pull/76) preserve
this result for the next sync. Initial comparison commits are store
`4531e46c383a94db3119dc7e6917bc2c32fc9d26` and website
`9c37849de420ce5434de39eff0272286d98a9a89`; the following context-only commit
adds these PR receipts. Both ownership PRs remain unmerged.

Combined checks passed: 174 relative links, eight paired-tree draft links, ten
available anchors, 14 website manifest paths, JSON, fences/newlines, and
changed-line whitespace. Independent review confirmed the source comparison
and corrected the reciprocal ADR anchor. Existing CI was inspected before the
planning merges: website validation reported 37 formatting errors and dependency
review reported unsupported/Dependency graph; store Quality gates passed and
E2E failed at the ambiguous Black / Small locator. Refresh the new PR checks;
none of this asserts that new runtime/provider tests passed.

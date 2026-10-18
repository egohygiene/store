# Current handoff

## Four-digit labels — 2026-10-18 UTC

Five inline decision labels and current links are padded under [Hygiene #73](https://github.com/egohygiene/hygiene/issues/73), with a per-record map in root DECISIONS.md. Inverse-mapped body comparison and documentation link/diff checks pass. This bounded change preserves the historical ownership checkpoint below; refresh its live task state before resuming. No code, provider or deployment evidence is added.

Snapshot: **2026-10-17 UTC**. Ownership comparison and review checkpoint;
no deployment or source migration.

| Record | State |
| --- | --- |
| Repository | `egohygiene/store` |
| Source implementation inspected | `599c90ca6a454c0f2e9aa95eab5f8395016474c5` |
| Planning PR | [Store #33](https://github.com/egohygiene/store/pull/33), merged at `bfda1a7c6b0ce09258522be8d8fe4bf9cba8b5a3` |
| Paired planning PR | [Website #74](https://github.com/egohygiene/egohygiene.io/pull/74), merged at `ee59e2f83c59c084c23a5f8bcc3311c2dc830859` |
| First authorized issue | [Website #75](https://github.com/egohygiene/egohygiene.io/issues/75) |
| Ownership review PRs | [Store draft #34](https://github.com/egohygiene/store/pull/34) and [website draft #76](https://github.com/egohygiene/egohygiene.io/pull/76); both open/unmerged at this checkpoint |
| Ownership review branch | `docs/storefront-ownership-75` in both repositories; refresh PR state before resuming |
| Selected direction | Website app owns V1 storefront; one composed site build; this repository remains a preserved commerce reference |
| Next decision | Review the paired ownership drafts, then continue the approved implementation queue |

Start with the [latest dated receipt](2026-10-17-storefront-ownership.md),
[canonical comparison](https://github.com/egohygiene/egohygiene.io/blob/docs/storefront-ownership-75/docs/architecture/storefront-ownership.md),
and [ADR-0005](../../DECISIONS.md#adr-0005-select-the-website-as-the-v1-storefront-owner).
The [October 16 discussion](2026-10-16-store-launch-discussion.md) remains
historical context. The planning PRs are merged; its earlier approval gate is
superseded only for the authorized first ownership issue. The wider
[roadmap proposal](https://github.com/egohygiene/egohygiene.io/blob/ee59e2f83c59c084c23a5f8bcc3311c2dc830859/docs/roadmaps/store-launch.md)
still needs review before bulk issue/milestone creation or reorganization.

## Boundaries to preserve

- `/` presents Ego Hygiene; `/store` is community commerce. `.play()` is a
  featured artist. Curated designs and the large song-merch catalog keep
  separate browsing surfaces and stable song destinations.
- The website's approved public projection, catalog identifiers, and portable
  domain remain the selected app boundary. Private merch/music source
  repositories are not moved or exposed.
- This repository's code, mock environment, issues, history, and MIT notice
  remain available. Selective reuse needs immutable provenance and qualification.
  No app is deleted, repository archived, or code copied by this checkpoint.
- Netlify development preview after merges into `development` remains preferred;
  website #29 owns CI/hosting work. Production hosting is still Google versus
  Cloudflare. This review activates no workflow, credential, or infrastructure.
- Fourthwall remains the first merchandise candidate and hosted checkout stays
  the V1 boundary. Provider configuration does not prove an order. Store #32
  retains cart/handoff qualification work; comics and campaigns follow later.

## Next checkpoint

1. Refresh both repository heads and paired ownership PRs. Review the comparison,
   preservation inventory, successor ADRs, and cutover/rollback criteria.
2. After acceptance, replace active draft links with merged immutable evidence
   and mark the successor ADRs accepted without rewriting historical records.
3. Continue website #29 CI/preview work. Resolve website licensing ambiguity
   before importing substantial MIT source; retain the original notice.
4. Map useful commerce behavior into website contracts under existing issues.
   Keep source research, provider qualification, and deployment evidence distinct.

## Verification and limits

Source and test files were inspected at immutable revisions. Documentation
verification covers links, structure, and whitespace. No new application tests,
live provider sessions, checkout, payment, fulfillment, or deployment results
are claimed. The dated receipt records scope and evidence for the next chat.

A fresh chat can start with: "Read AGENTS.md and docs/context/current-state.md
in egohygiene/store and egohygiene/egohygiene.io, refresh issue #75 and the paired
ownership PRs, then resume the next approved checkpoint."

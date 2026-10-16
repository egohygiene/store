# Current handoff

Snapshot: **2026-10-16**. Discussion capture, not deployment completion.

| Record | State |
| --- | --- |
| Repository | `egohygiene/store` |
| Source main inspected | `599c90ca6a454c0f2e9aa95eab5f8395016474c5` |
| Website source inspected | `egohygiene/egohygiene.io` at `db634b887ede348ce85d9c03af789467ab535dcf` |
| Intended review branch | `docs/store-launch-direction-20261016` |
| Work | Documentation-only capture; PR/merge state must be refreshed on GitHub |
| Next decision | Review the proposed milestone/issue hierarchy before creating issues |

Read the [dated checkpoint](2026-10-16-store-launch-discussion.md) for granular
conversation context, and [ADR-004](../../DECISIONS.md#adr-004-preserve-the-community-store-direction-and-reconcile-deployment-ownership)
for the durable direction. The
[canonical launch-plan draft](https://github.com/egohygiene/egohygiene.io/blob/docs/store-launch-direction-20261016/docs/architecture/store-launch-plan.md)
lives in the website repository. Its branch link is intentional while review is
pending; record the merged commit and update the pointer after integration.
The [proposed milestones and sub-issues](https://github.com/egohygiene/egohygiene.io/blob/docs/store-launch-direction-20261016/docs/roadmaps/store-launch.md)
map existing work in both repositories. They are review input, not created issues.

## Preserve these distinctions

- Ego Hygiene owns the site's primary mission and future product. Community
  commerce belongs at `/store`; `.play()` is a featured artist. Curated
  standalone designs and the roughly 400-song merch catalog need separate
  browsing surfaces, with stable song destinations for SoundCloud links.
- Both repositories contain store implementations. This repository's ADR-003
  favors independent deployment; the website's high-level ADR-004 favors an
  integrated store. Neither has been silently superseded.
- Local development plus a hosted Netlify preview after merges into
  `development` is the preferred workflow. Reusable GitHub Actions are desired;
  the branch, protection rules, credentials, and workflow are not configured by
  this checkpoint. Production hosting remains Google versus Cloudflare.
- Fourthwall is the first merchandise candidate. Provider qualification and
  checkout verification remain work. Comics and Alpal start as development
  pages; Lulu and Makeship remain candidates for later relevant offerings.
- Keeping private merch/design sources separate is the recommendation. The
  discussion grants no repository transfer or public release of private assets.

## Next checkpoint

1. Refresh both source heads, current PRs, and actual checks; preserve new work.
2. Review the proposed milestones and parent/child issue structure with the
   user. Create or reorganize issues only after approval, reusing existing IDs
   and preserving their historical parents and evidence. Then sync again.
3. Once implementation is authorized, compare routing, catalog/contracts,
   provider adapters, cart behavior, tests, and assets. Name one canonical store
   with a preservation plan for useful work in the other repository.
4. After ownership is settled, specify the deployment coordinator and preview
   acceptance checks. No production platform is assumed.

## Validation and limits

This capture changes Markdown only. Source and existing architecture were read.
Documentation checks cover relative link targets against the complete source
tree, available local anchors, balanced fences, whitespace, and file endings.
Application, browser, provider, and deployment tests were not run. No
purchase, provider activation, infrastructure change, issue creation, or
repository transfer is claimed. Git history and the eventual PR hold the
documentation diff and review evidence; refresh those before resuming.

A fresh chat can start with: "Read AGENTS.md and docs/context/current-state.md
in egohygiene/store and egohygiene/egohygiene.io, refresh the linked revisions
and PRs, then resume the next approved checkpoint."

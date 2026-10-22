---
name: refresh
description: Maintainer-only. Update one domain catalog snapshot from a named source. Use only when the user asks to refresh, update, or add a domain pack. Never during a prototype fill.
disable-model-invocation: true
---

# Refresh a domain catalog

This skill writes schema **shape** into `catalogs/<id>/`. It never runs as part of fill.

## Hard stops

1. Run only when the user names this job (refresh, update the pack, add a domain).
2. Read `catalogs/index.json`. The target `id` must already be listed. Adding a new domain requires the user to approve a new `index.json` row first.
3. Write only under `catalogs/<id>/`. Never into `artifacts/`.
4. Copy **shape** only: entities, fields, enums, formulas, screen column lists. Never customer or sandbox **rows**.
5. Set `domain.json` `snapshot.captured` to today. Keep `sourceRepo` as a citation. Fill must still not fetch that repo.
6. Flip `ready` to `true` in both `domain.json` and `index.json` only when the pack has `whenToPick`, fields, and at least one screen (or an explicit “no screens yet” note the user accepted).
7. Do not invent enums that are not in the source.

## After the refresh

Say which pack changed, what was added, and that fill still uses the snapshot only.

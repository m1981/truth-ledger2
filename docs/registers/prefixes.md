# Prefix register — the single allocation authority for identifier spaces

Per constitution C5: no identifier space exists before a row here.
ISO/IEC 11179's move applies: the registry is itself registered — it is
the first row of its own table, so its own staleness is somebody's job.

| Prefix / space | Meaning | Allocated | Status |
|---|---|---|---|
| (this file) | prefix allocation authority | 2026-08-31 | live |
| `CMP-NNN` | complaints, `docs/complaints/` | 2026-08-31 | live |
| `F-N` | candidates, `docs/candidates.md` | 2026-08-31 | live |
| `SC-<slug>-NNN` | spec assertions (F-2, `tl2 mirror`) | 2026-08-31 | live (F-2 bought 2026-09-01, CMP-005) |
| `cap-<hex8>` | evidence capsules, `capsules.jsonl` (content-hash ids, per installation) | 2026-08-31 | live |
| `ret-<hex8>` | capsule retraction tombstones, `capsules.jsonl` (content-hash ids, per installation) | 2026-09-01 | live |

Rules:

- A prefix is a name, not an index: never reused, never renumbered.
- Client installations receive their own prefix at initialization, from
  this table, so two installations can never collide.
- Retiring a prefix is a row-status change with a date, never a row
  deletion.

## Installations

| # | Repository | Engine version pinned | Initialized | Status |
|---|---|---|---|---|
| 1 | this repository (dogfood) | HEAD (engine-dev runs hot, by design) | 2026-08-31 (CMP-002) | live |
| 2 | `~/PycharmProjects/kuchnie` (github.com/m1981/kuchnie) | v0.1.1 | 2026-09-01 (operator ruling O1, after the v1 freeze there; re-pinned same day after the slug-scoping fix its own first run bought) | live |

Installation state (capsules.jsonl, its cap-/ret- ids) never leaves
its repository (scope R5) and stores are never merged across
installations, so content-hash ids cannot collide between them.
- Declared gap: nothing enumerates this register's population from
  reality (no sweep checks that every id space in use has a row). v1
  ended up needing exactly that sweep. Until a complaint buys one, this
  sentence is the honest record of that gap.

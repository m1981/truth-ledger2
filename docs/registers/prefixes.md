# Prefix register — the single allocation authority for identifier spaces

Per constitution C5: no identifier space exists before a row here.
ISO/IEC 11179's move applies: the registry is itself registered — it is
the first row of its own table, so its own staleness is somebody's job.

| Prefix / space | Meaning | Allocated | Status |
|---|---|---|---|
| (this file) | prefix allocation authority | 2026-08-31 | live |
| `CMP-NNN` | complaints, `docs/complaints/` | 2026-08-31 | live |
| `F-N` | candidates, `docs/candidates.md` | 2026-08-31 | live |
| `SC-<slug>-NNN` | spec assertions (candidate F-2) | 2026-08-31 | reserved until F-2 is bought |

Rules:

- A prefix is a name, not an index: never reused, never renumbered.
- Client installations receive their own prefix at initialization, from
  this table, so two installations can never collide.
- Retiring a prefix is a row-status change with a date, never a row
  deletion.
- Declared gap: nothing enumerates this register's population from
  reality (no sweep checks that every id space in use has a row). v1
  ended up needing exactly that sweep. Until a complaint buys one, this
  sentence is the honest record of that gap.

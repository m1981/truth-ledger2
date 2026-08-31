# Gate metrics — every gate's birth record, catches, and probation date

Per constitution C3: a gate is born with this row, counts its catches
and false alarms, and is removed by its own record if it catches
nothing by its probation date. Per C2, "witnessed" means both halves:
seeded red AND a recorded corpus test of plausible legitimate traffic.

| Gate | Tier | Bought by | Born | Witnessed red | Corpus test | Catches | False alarms | Probation |
|---|---|---|---|---|---|---|---|---|
| `scripts/githooks/commit-msg` | engine-dev | CMP-001 | 2026-08-31 | 2026-08-31 (seeded: the CMP-001 message itself) | 2026-08-31: 10 plausible English messages (incl. three about the Jest framework), 10 pass / 0 false alarms; known accepted miss: diacritic-free Polish (documented tradeoff) | 0 | 0 | 2026-11-30 |

Counting rules:

- A catch is a rejected message that was genuinely Polish; a false
  alarm is a rejected message that was not. Both are one-line edits to
  this table, made in the same session that saw the event.
- Probation dates are swept by people, not hope: **any session that
  edits a gate or this file checks every probation date first** and
  retires what its record has already killed.
- A false alarm is recorded FIRST, then overridden: the metrics entry
  and the `--no-verify` belong to the same commit.
- `--no-verify` is an **unregistered escape**: nothing detects an
  override that was not recorded here, and this register cannot count
  what bypasses it. v1 needed a whole waiver register for this class.
  Until a complaint buys better, this sentence is the honest record of
  that gap.

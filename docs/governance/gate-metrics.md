# Gate metrics — every gate's birth record, catches, and probation date

Per constitution C3: a gate is born with this row, counts its catches
and false alarms, and is removed by its own record if it catches
nothing by its probation date. Per C2, "witnessed" means both halves:
seeded red AND a recorded corpus test of plausible legitimate traffic.

| Gate | Tier | Bought by | Born | Witnessed red | Corpus test | Catches | False alarms | Probation |
|---|---|---|---|---|---|---|---|---|
| `scripts/githooks/commit-msg` | engine-dev | CMP-001 | 2026-08-31 | 2026-08-31 (seeded: the CMP-001 message itself) | 2026-08-31: corpus file `commit-msg-corpus.txt` (10 plausible English messages, incl. three about the Jest framework), replay: `while IFS= read -r m; do printf '%s\n' "$m" > /tmp/m.txt; sh scripts/githooks/commit-msg /tmp/m.txt; done < docs/governance/commit-msg-corpus.txt` — 0 false alarms; known accepted miss: diacritic-free Polish (documented tradeoff) | 0 | 0 | 2026-11-30 |
| `scripts/tl2 check` | client | CMP-002 | 2026-08-31 | 2026-08-31, three seeded faults, each caught: unresolvable anchor → SUSPECT (fail-closed); watched path changed since anchor → SUSPECT; tampered output hash → STALE. One seed was itself broken on first run (watched a path unchanged since its anchor, came back OK) and was corrected — the witness discipline caught its own bad seed | 2026-08-31: three legitimate capsules on clean committed paths (scope refusal count, constitution rule count, AGENTS rule count) → all OK, exit 0. During testing the tool also correctly flagged capsules watching uncommitted paths as SUSPECT — fail-closed on dirty trees confirmed, not counted as false alarms | 0 | 0 | 2026-11-30 |

Counting rules:

- A catch is a rejected message that was genuinely Polish; a false
  alarm is a rejected message that was not. Both are one-line edits to
  this table, made in the same session that saw the event.
- **Misses are counted too**: a defect a gate exists to catch that got
  past it is recorded in that gate's row, in the session that saw it.
  A metrics table without misses inflates every gate — v1's most honest
  number (its 1.5% verification hit rate) existed only because
  recording misses was mandatory.
- Probation dates are swept by people, not hope: **any session that
  edits a gate or this file checks every probation date first** and
  retires what its record has already killed. Named tension: this is a
  prose rule, and CMP-001 established that prose does not bind an
  agent at the moment of acting — the sweep will happen only if
  someone's attention lands here. Until a complaint buys a mechanical
  sweep, this sentence is the honest record of that gap.
- A false alarm is recorded FIRST, then overridden: the metrics entry
  and the `--no-verify` belong to the same commit.
- `--no-verify` is an **unregistered escape**: nothing detects an
  override that was not recorded here, and this register cannot count
  what bypasses it. v1 needed a whole waiver register for this class.
  Until a complaint buys better, this sentence is the honest record of
  that gap.

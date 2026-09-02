# Mechanisms — the architect's inventory: what each level does, and how

> Reader: an architect or new session asking "what actually runs here,
> at which level, implemented how, and who watches it" | Enables:
> holding the whole machine in one read without opening code |
> Update-trigger: a mechanism is bought, retired, or re-implemented —
> `tl2 whisper docs/mechanisms.md` will say so before you edit

Status: DESCRIPTIVE — this file explains, it never authorizes; the
authoritative records are the metric register (birth, witnesses,
counts) and the complaints (what bought each). The ladder below is the
meta-level stratification: **each level exists because the level below
it was caught lying** (L1 born of lying sentences, L2 born of lying
guards).

## L0 — mechanisms about SENTENCES (what is true, and how to pin it)

**Capsule + check** (F-5; `scripts/tl2` verbs `capsule`, `check`).
*Does:* binds a sentence to a receipt — evidence command, sha256 of
its output, witness commit, watched paths — then recomputes trust at
every read: anchor gone → SUSPECT (fail-closed); watched path touched,
even uncommitted → SUSPECT; re-run hash differs → STALE. Nothing is
stored but the records; status is always a projection.
*Implementation:* append-only JSONL (`capsules.jsonl`) + `git
diff/status/cat-file` at read time.
*Two defining absences, both cut from the founding idea by
measurement:* no clock — elapsed-time demotion (v1's TTL) was the
false-alarm engine and is a declared dead zone until a complaint buys
it; and no inferred relevance — the invalidation scope is DECLARED by
the author (watched paths), never guessed by the engine, because v1's
relevance-guessing scan measured 16 firings, 0 correct.
*Observed by:* its own metric row; the maintenance-loop runbook guard
watches the verbs' source.

**Retract** (CMP-017; verb `retract`).
*Does:* retires a wrong or superseded capsule without deletion — a
tombstone with cause and successor; `check` reports it, never reddens;
`whisper` falls silent for it. History stays readable as history.
*Implementation:* `ret-` records in the same JSONL, folded at read.

**Criticality tiers** (F-6; file `criticality.tiers`).
*Does:* prices attention by consequence — path prefixes classed
money/auth/data-integrity/compliance/plain by a dated operator ruling;
no ruling means everything plain, so unearned rigor never engages.
*Implementation:* a five-line parser inside tl2; consumed by whisper
and ready.

## L1 — mechanisms about GUARDS OF WORK (does the code keep the sentences' promises)

**Mirror** (F-2; verb `mirror`).
*Does:* bidirectional traceability at grep weight — manifest ids vs
ids cited in test-shaped files; a promise no test cites is a GAP, a
citation of no promise is an ORPHAN, either reds.
*Implementation:* two set differences over a directory walk; citation
scope limited to `test_*`/`*_test.*` (CMP-020 — the spec's own inline
ids must not satisfy the scan).

**Vacuity** (F-3; verb `vacuity`).
*Does:* asks whether a test can die: overlays the working-tree test on
the pre-change tree; assertion failure there = PROVEN (evidence),
green-on-both = counted but no evidence, import/collection error =
INCONCLUSIVE, never red.
*Implementation:* `git archive` into a scratch tree + runner exit-code
convention (0/1/other).

**Whisper** (F-8; verb `whisper`).
*Does:* context injection at the moment of action — before you touch a
path, names every capsule watching it; non-plain classes tagged and
spoken in full, plain budgeted to three lines (`--all` lifts). Fail-open:
never blocks, never errors on content.
*Implementation:* prefix match over capsule watch-lists + tiers file.
*Declared gap:* delivery today is runbook prose — the agent calls
whisper by discipline; the harness pre-edit wiring F-8 designed (a
PreToolUse hook injecting the warning automatically) is a hook, so C1
holds: it awaits the first edit that hurt because whisper was skipped.
Until then this sentence is the honest record — and the irony is
named: F-8's own mechanism is delivered by the channel F-8 exists to
replace.

**Ready** (F-12; verb `ready`).
*Does:* the derived queue — open complaints, probation countdowns
(OVERDUE flagged), non-OK capsules with critical ones first; answers
"what now" so no operator turn is spent asking.
*Implementation:* read-time fold over the complaints dir, the metric
table's dates, and `check`'s projections; never hand-maintained.

**Commit-msg gate** (CMP-001; `scripts/githooks/commit-msg`,
engine-dev).
*Does:* refuses Polish commit messages — red at ≥2 diacritic words;
its false-alarm protocol (record first, then `--no-verify`) is printed
in its own refusal.
*Implementation:* one `tr|grep -c` pipeline in sh; corpus file
committed beside it for replay.

**Lint, proposer only** (F-1; verb `lint`).
*Does:* makes spec sentences able to die — mechanically EXTRACTS
candidate normative lines (extraction suggests, never judges), hands a
fresh session the judgment plus a report skeleton; intake gates only
the report's shape (marker, limit line, findings, SC- proposals). The
ruled keyword-gating layer measured empty and stays unbought.
*Implementation:* keyword regex for extraction; string checks for
intake.

**Verify** (F-4; verb `verify`).
*Does:* the fresh-context verifier ceremony's mechanical halves —
brief with the duty to go beyond the recipe; intake refusing a report
without the `proposed-by: llm` marker, the independence-limit line, or
a valid verdict. The verdict itself never gates; a human disposes.
*Implementation:* brief generator over a capsule record + string-shape
intake; dispatch criteria live in `runbooks/verifier.md`.

## L2 — mechanisms about THE GUARDS THEMSELVES (who watches the watchers)

**Birth discipline C2+C3** (constitution; ledger:
`docs/governance/gate-metrics.md`).
*Does:* no guard may block before being witnessed red on a seeded
fault AND green on a representative corpus; every guard is born with
counts (catches / false alarms / misses) and a probation date, and
dies by its own record.
*Implementation:* law plus one markdown table; `ready` surfaces the
probation dates.

**Separation canary** (F-7; `scripts/separation-canary`, engine-dev).
*Does:* proves the engine/installation boundary before each release —
installs the client tier into a sandbox, runs every verb, reds on any
access outside it. Blocked its first release (its own fixture had
gone stale) — working as designed.
*Implementation:* three independent detectors — a Python audit hook on
the verb process's opens, an mtime sweep over the engine repo, a
`git status` diff; subprocess reads declared untraced.

**Guard capsules on documents** (instances of F-5 doing L2 duty).
*Does:* every load-bearing document (diagrams, runbooks, architecture,
this file) is watched by a capsule pinning a countable property and
watching BOTH the document and what it depicts — either side drifts,
the pair goes SUSPECT before anyone trusts a stale picture. The
lexicon family's guards pin the subtlest property of all: that a
dictionary stays non-normative.
*Implementation:* ordinary capsules; the maintenance loop
(successor-first) is their choreography.

## The one-sentence architecture

L0 pins what is true; L1 checks that work keeps its promises; L2
checks the checkers — and every mechanism on this page was bought by a
named harm, witnessed both ways, and is counted in the register that
can also kill it. The founding idea (a cache-invalidation system for
agent-asserted sentences) survives as L0's capsule — and L2 exists
because the system stopped exempting that idea from itself.

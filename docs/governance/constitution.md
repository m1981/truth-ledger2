# Constitution — how anything enters this system

Status: **ACCEPTED** (operator ruling of 2026-08-31, together with
`docs/scope.md`).

Scope (`docs/scope.md`) says what this system refuses to be. This file
says how anything gets in. Six rules. Every rule below was bought by a
measured failure in truth-ledger v1; the purchase is named so a future
reader can check whether the reason still holds.

**C1 — No mechanism without a complaint.** A gate, register, hook, or
instrument enters only with a reference to a filed complaint
(`docs/complaints/`) naming the concrete harm that bought it.
*Bought by:* v1 accreted ~60 ADRs of machinery bottom-up from pain,
with no floor for "no" — the scope card arrived on **day ~50**, not
day 1 (measured 2026-08-31: first commit 2026-07-07 = v1@cea54e9,
scope ruled 2026-08-26 = v1@28f91a2). `[corrected — CMP-003: originally
written as "day ~200", an unverified transplant of another agent's
rhetoric]`

**C2 — A gate proves it can fail AND proves it can stay quiet, before
it may block.** Two witnesses, both recorded: a seeded fault turning
the gate red, and a **corpus of plausible legitimate traffic passing it
green** with the false-alarm result written down. A gate that has never
been red proves nothing; a gate witnessed red on one seeded fault and
never tested against realistic traffic is half-witnessed.
*Bought by:* the v1 narrow-regex incident (a traceability check whose
regex did not know the conventions it policed reported 13 false
failures out of 15) `[unverified here — lives in v1 session records]` —
and re-bought at this repository's own founding, when its first gate
shipped a word list containing "jest" and blocked three plausible
English commit messages about the Jest framework; the collision was
found by external review, not by the author's seeded test
`[verified — this repository's own record]`.

**C3 — Every gate is born with a metric and a probation date.** Catch
and false-alarm counts from day one; a gate that catches nothing by its
probation date is removed by its own record. Alarm fatigue kills
verification tools faster than missing features.
*Bought by:* v1's post-commit hook, killed at 3.6% PPV; and the 1.5%
verification hit rate the system honestly reported against itself
`[confirmed by external review, 2026-08-31]`.

**C4 — The engine verifies itself only through the public surface.**
This repository's own installation, when it exists, uses exactly the
entry points, manifests, and client-side gates a customer installation
gets. Dev-side rigor is additional rigor over the engine, never a
private alternative surface.
*Bought by:* an external reviewer mistook v1's internal battery for the
buyer's cost — the two tiers were not labeled. Battery size: 14 arms
circa 2026-08-21 (the incident's era, per v1 session records), **17 as
of 2026-08-31** (v1@HEAD, `grep -c '^echo "ARM'
scripts/test-release-battery.sh`). `[corrected — CMP-003: originally
cited as "14-arm battery", undated]`

**C5 — No identifier space before a register row.** Any new ID scheme
(prefix, numbering) is allocated in `docs/registers/prefixes.md` before
first use.
*Bought by:* three v1 registers independently allocated EPI-001..031 to
different principles; every session locally-rationally started at 001
`[unverified here — lives on a v1 branch]`.

**C6 — Two gate tiers, labeled at birth.** Every instrument declares
`tier: engine-dev` (lives here, never installs) or `tier: client`
(ships, minimal, scope-gated). An unlabeled instrument does not enter.
*Bought by:* same incident as C4 (its citation, correction included,
applies here too).

## Erratum: what these purchase records are (operator ruling, 2026-08-31, CMP-003)

The records above are **frozen provenance**: dated citations anchored
to v1 commits, labeled `verified` / `unverified here` / `corrected`.
The engine will never recompute any of them — by construction: R5
keeps state inside the installation and watched paths cannot reach
another repository's tree, so a cross-repository sentence has no
carrier in this model. That dead zone is permanent and declared
(CMP-003, the register's first declined complaint). Since the founding
exception closed, the rules' authority rests on the operator's
ratification, not on these numbers: a false number is corrected as a
dated erratum — it does not un-buy a rule. Two of six records were
false within a day of writing; the corrections above are the record of
that.

## The founding exception is closed

The six rules above were bought with a second currency: lessons of
truth-ledger v1, which have no register here and are not falsifiable
inside this repository. Ruling (operator, 2026-08-31): that currency
was **valid once, at founding, and is closed**. From that ruling
forward the only purchase currency is a filed `CMP-` complaint; an
appeal to "a v1 lesson" buys nothing.

## Order of work (binding)

1. A mechanism is preceded by its complaint (C1), enters through both
   C2 witnesses, and is born with its C3 row.
2. Design ahead of purchase is legal only in
   `docs/candidates.md`, which is deliberately never ratified and
   carries its own falsifier clause. Ratified documents describe what
   is bought or what refuses; they do not describe futures.
3. Rulings are the operator's, dated, and separate from drafting —
   including in time: a document drafted and ruled the same day is a
   ceremony compressed past its purpose, and this repository's own
   founding proved it (both external reviews arrived after a same-day
   ratification and reopened ACCEPTED documents).

# Candidates — a reasoning record, deliberately never ratified

Status: **REASONING RECORD.** This document is not normative, carries
no ruling line, and never will. Its first founding shipped as a
ratified "feature map" with lifecycle statuses; an external review
correctly named the defect: DO-178C's objectives may predate every
project because a *standards body external to the project* wrote them —
a genome written by the same agent, in the same repository, on the same
day, is not that move. Eight designed features are eight attractors
that bend every future complaint toward them.

So this catalog exists on the opposite footing:

> **The falsifier clause.** A complaint that fits no row below is
> evidence about this catalog, not about the complaint. The catalog
> yields — a new row, or an amendment — and the complaint is never bent
> to fit. Bending a complaint toward an existing row is this document's
> named failure mode.

Rows are candidates: sketches of mechanics with a named buyer class.
None is a promise; none may have code (constitution, order of work,
rule 2); a purchase (C1) buys **one mechanism**, and file formats named
here are placeholders revisable without ceremony until built. Candidate
ids `F-N` are allocated in `docs/registers/prefixes.md`.

Each candidate names the DO-178-shaped distrust it would transplant —
the concrete way projects deceive themselves.

## Summary

| Id | Candidate | Distrust addressed | Tier | LLM role |
|---|---|---|---|---|
| F-1 | Spec testability lint | "we built the wrong thing, correctly" | client | proposer |
| F-2 | Bidirectional traceability mirror | "the code does more than was written" | client | none |
| F-3 | Test non-vacuity check | "the test passed and proved nothing" | client | none |
| F-4 | Fresh-context verifier | "the author cannot see their own blind spots" | client | reviewer |
| F-5 | Evidence capsules + suspect projection | "what shipped is not what was checked" | client | none |
| F-6 | Business criticality tiers | "uniform rigor is fake rigor" | client | proposer |
| F-7 | Separation canary | "the dogfood leaked into the product" | engine-dev | none |
| F-8 | Whisper (pre-edit warning) | "the rule was not in the actor's context at the moment of acting" | client | none |
| F-9 | Agent-concurrency discipline | "two sessions, one tree, somebody's work swept into somebody else's commit" | client | none |
| F-10 | Guard liveness | "the guard was deleted, or never had a reader, and nothing could tell" | client | none |
| F-11 | Decision propagation | "the decision changed and nothing reached the work and sentences standing on it" | client | none |
| F-12 | Work queue | "an operator turn was spent asking what now; finished work hid blocked work" | client | none |
| F-13 | Budget sense | "ceremony ate the subscription and nothing was counting" | client | none |

The eighth distrust — "the tool lied and we believed it" — is not a
candidate: it is constitution C2/C3, already law for every gate. The
first founding wrapped it as a feature to have something to call BUILT;
two reviews independently killed that.

## F-1 — Spec testability lint

**Transplants:** requirements analysis, the cheapest defect source in
IV&V (a requirements defect found at requirements costs 1×; at test,
10–50×; in production, 100×+ — Boehm-lineage figures, contested in
later empirical literature; order-of-magnitude only).

**Scope bridge (to be ruled at purchase, not before):** scope asks one
question — correspondence — and F-1 inspects a sentence before any
correspondence exists. The bridge: an untestable sentence can never be
correspondence-checked at all, so F-1 polices *eligibility* for the one
question. If the operator refuses the bridge at purchase time, only the
proposer layer may exist.

**Mechanics sketch.** Two layers with different authority. The
*mechanical* layer gates on syntax only: a sentence is normative iff it
contains a keyword from a declared, versioned list (default: shall,
must, always, never, only); a normative sentence containing a term from
the banned-vagueness vocabulary ("appropriate", "adequate", "fast",
"reasonable", "etc.") is red. Nothing else gates — "measurable object"
and clause-reachability are judgment-shaped and belong to the *LLM*
layer, which proposes: flagging sentences it judges untestable and
drafting their decomposition into `SC-` assertions (F-2's input), as
`proposed-by: llm` artifacts per architecture §6.

**Buyer class:** a spec sentence that could not be tested caused
rework, a dispute, or a shipped misunderstanding.

**Measured on the consumer corpus (2026-09-01, effectiveness review):**
the ruled gating layer produced **zero signal** over 21 specs — 107
normative lines, 0 red hits, precision undefined — while demonstrably
missing both QB-001's harmful sentence ("may" is not a listed keyword;
"any order" is not in the vocabulary) and the corpus's self-declared
untestables ("in minutes", screens.md:45). The proposer layer, demoed
on the same spec, produced seven usable SC decompositions. The
measurement says: if F-1 is ever bought, buy the proposer; the ruled
mechanical layer as scoped is empty on real traffic.

**Refuses:** judging whether a requirement is the *right* requirement
(scope R1).

## F-2 — Bidirectional traceability mirror

**Transplants:** bidirectional traceability (DO-178C trace-data
doctrine; bidirectional traceability per ISO/IEC/IEEE 29148) at grep
weight. Inherited from the v1 spec-coverage pilot —
a history **unverified in this repository** and re-falsified at build
time, not trusted on citation.

**Mechanics sketch.** Testable assertions get ids `SC-<slug>-NNN`
(prefix reserved in the register), present both inline in the spec and
as one line of a sibling manifest (`<spec>.sc.txt`, sorted, headerless).
Tests cite the id as the first docstring line. Two set-difference
checks, one per direction: a manifest id no test cites is a coverage
gap; a cited id absent from the manifest is an orphan. Both directions
red by default.

**Buyer class:** a spec assertion shipped with no test, or a test cited
an assertion that did not exist, and somebody paid for the gap.

**Measured on the consumer (2026-09-01):** fast (five manifests, both
directions, under five seconds) and the ORPHAN direction earns its
keep — but the GAP direction is structurally dead in the shipped
layout (inline spec ids satisfy the citation scan: CMP-020), and 16 of
21 consumer specs carry no manifest at all. Effectiveness today:
typo/phantom citations and manifest↔spec drift, not untested
assertions.

**Refuses:** measuring *how well* a citing test exercises its assertion
(that is F-3's distrust; beyond it, structural coverage, refused by
scope R3).

## F-3 — Test non-vacuity check

**Transplants:** the doctrine that a test which has never failed proves
nothing (v1's EPI-302; mutation testing's premise).

**Mechanics sketch.** For a new or changed test, materialize the
pre-change tree (`git show` into a scratch dir) and **overlay the new
test file onto it** — the test is always the new one, the code under
test always the old. Only an **assertion failure counts as the
witnessed red**: a collection, import, or missing-fixture error is an
*inconclusive* run carrying zero evidence, reported as inconclusive.
**Green-on-both passes** — on a refactor it is the norm, and reddening
it is guaranteed alarm fatigue — but the run is counted, and a rising
share of green-on-both runs is the recorded signal to consider buying
mutation-lite (a separate purchase).

**Buyer class:** a green test that asserted nothing, or a defect that a
supposedly-covering test missed.

**Refuses:** coverage percentages of any kind (scope R3).

## F-4 — Fresh-context verifier

**Transplants:** the *rationale* of IEEE 1012 technical independence —
a fresh viewpoint on the work — while supplying none of 1012's three
independence parameters: technical, managerial, financial. In 1012's
frame a fresh session of the same model is the same tool; what F-4
buys is independence of the author's **context**, which 1012 does not
name as an axis.

**Mechanics sketch.** A claim marked for verification is handed to a
fresh LLM session inheriting nothing from the author: the claim, its
capsule recipe, repository access. The reviewer re-derives the evidence
and files a report artifact per architecture §6, with the mandatory
limit header (independent in context, not in failure). The report never
gates; a human disposes.

**Buyer disclosure (required if this ever ships):** the marker and
report discipline is enforceable only for artifacts that carry it —
architecture §6's honesty block applies verbatim, and the buyer is told
so in the product, not in a footnote.

**R2 bridge (to be ruled at purchase, not before).** Scope R2 says a
judgment-shaped check "does not enter the engine" — not merely "does
not gate" — and F-4 is LLM-driven and ships at client tier. The bridge:
F-4 is not a *check* under R2, because it computes no status and blocks
nothing; it produces a proposal artifact a human disposes of
(architecture §6). If the operator reads R2 stricter at purchase time,
F-4 retiers to engine-dev or only its report format survives. The
reconciliation is declared here, not achieved — exactly like F-1's
scope bridge, it is a ruling item, and buying F-4 without ruling on it
is invalid.

**Buyer class:** an author-verified claim later proven false — the
author's own confirmation was the failing control.

**Refuses:** claiming IEEE 1012 independence (all three axes —
technical, managerial, financial — are structurally absent and
declared so, not simulated).

## F-5 — Evidence capsules + suspect projection

**Transplants:** configuration audit ("what flew is what we checked":
FCA/PCA, reproducible builds, in-toto/SLSA provenance) applied to
sentences.

**Mechanics sketch.** A capsule binds: the sentence, the command that
evidences it, the hash of that command's output, the commit anchor, and
the watched paths. Appended to `capsules.jsonl`. Recheck re-runs and
compares hashes. Suspect is a read-time projection with the three
failure modes named in architecture §2 (fail-closed on unreachable
anchor; integrity and watched-set adequacy declared).

**Buyer class:** a recorded, believed sentence went stale silently and
someone acted on it.

**Refuses:** capsules over judgments ("the design is clean") — the
command must be deterministic and its output hash-comparable, or the
sentence is not capsule material (scope R2).

**Retraction (bought by CMP-017):** a wrong or superseded capsule is
never deleted — `tl2 retract` tombstones it with a cause and an
optional successor id (v1's COPE-shaped ceremony, inherited at last);
`check` reports it without reddening and `whisper` falls silent. The
maintenance loop for every legitimate edit of a watched source, in
mechanical order (retract validates that a named successor exists, so
the successor comes first — the 2026-09-01 loop learned this by
leaving four tombstones without successor links): whisper before the
edit; after committing the edit, file the successor at the new anchor;
then retract the outdated guard naming that successor.

**Authoring doctrine (bought as doctrine by CMP-015, not as a
mechanism):** do not capsule sentences that pin volatile counters —
"the gate has six detectors" dies at every intentional improvement,
and the consumer measured five file→retract→successor cycles in one
day for zero information. v1's own late doctrine: "stop instructing
agents to file facts that are engineered to die." Capsule the
*property*, not the count, wherever the property is what you mean.

## F-6 — Business criticality tiers

**Transplants:** DO-178's level A–E proportionality — rigor priced by
consequence, decided before work.

**Mechanics sketch.** The installation carries a classification file
mapping paths to business criticality classes: `money`, `auth`,
`data-integrity`, `compliance`, `plain`. Client-tier gates read it and
scale. The LLM may propose a classification (`proposed-by: llm`); the
operator ratifies — unratified means every path is `plain` and gates
stay minimal, because unearned rigor is how alarm fatigue starts.

**Buyer class:** an alarm-fatigue complaint (checks crying wolf on
trivial paths) or a miss on a path that deserved more than it got.

**Refuses:** inferring criticality silently — classification is an
operator ruling, recorded and dated.

## F-7 — Separation canary

**Transplants:** the engine/installation boundary made falsifiable
(architecture §4).

**Mechanics sketch.** Install the client tier into a sandbox with no
access to the engine repository; run every client-tier verb that exists
at run time; trace file access; any read outside the sandbox is red.
Runs engine-dev-side on release tagging.

**Buyer class:** an installation observed reading outside its
repository, or a client artifact found depending on an engine-dev file.

## F-8 — Whisper (pre-edit warning)

**Transplants:** the *actor* comes from no standard — that half is
v1's own invention — but the *delivery* has ancestors: state-based
(dynamic) alarming (ISA-18.2/EEMUA-191), electronic checklists, and
computer-based procedures all deliver the rule at the moment and state
of action. DOORS is closer than a batch report too: it surfaces
suspect-link flags in the module view at read/edit time. The honest
contrast is pull versus push — DOORS shows suspicion to a human who
opens the module; whisper writes it into an actor's context that is
being constructed. What remains new is an actor whose attention is a
writable context. It is also the direct remedy for CMP-001's
root cause: a prose rule does not bind an agent that is not re-reading
it at the moment of acting — whisper makes the moment of acting carry
the rule.

**Mechanics sketch.** A pre-edit hook (agent-harness integration —
e.g. Claude Code hooks — or an editor/CI shim): before an edit touches
path P, answer "which capsules watch P" from `capsules.jsonl` (a cheap
read-time projection, like `check`). Two phases with opposite
polarities, inherited from v1's measured design: **deny** (declared
frozen paths, fail-closed) and **whisper** (fail-open, fatigue-budgeted:
high-priority capsules full voice, the rest one line). The fatigue
budget is not optional — v1 measured that an unbudgeted whisper is
alarm fatigue with extra steps.

**Buyer class:** an agent edited a watched path, the capsule went
SUSPECT, and nobody noticed until a later `check` — or a path that
should have been frozen was edited outright.

**Refuses:** blocking edits on judgment (deny is path-list mechanical);
whispering to humans as a nag channel — this is context injection for
agents, not a notification system.

## F-9 — Agent-concurrency discipline

**Transplants:** nothing — DO-178's configuration management assumes a
single change stream governed by humans. v1 measured what standards
never met: multiple model sessions working one tree concurrently.
Its incidents are the design input: a pathless `git add` swept three
sessions' hunks into one commit under one author; documents landed
without their code; a session's whole contribution entered history
under other sessions' names.

**Mechanics sketch.** Three mechanical parts, separable purchases:
single-writer rule per store (a store names its writing session while
open); append-only stores with content-hash ids so branch work merges
by union (already true of `capsules.jsonl` by construction); a
pre-commit guard that warns when staged hunks touch paths another live
session has declared open. Session attribution as a record field, so
history keeps who-did-what without archaeology.

**Buyer class:** the first harm from two sessions working this tree
concurrently — work swept into another session's commit, a store
written by two writers, attribution lost.

**Refuses:** locking (an agent that can be blocked by a stale lock is
worse than a merge); any central coordinator — confluence over
coordination.

## F-10 — Guard liveness

**Origin: the falsifier clause working as written.** Two harvested
events fit no row and forced this one (operator ruling, 2026-09-01):
CMP-013 (v1's battery regression gate deleted in a cleanup; absence
undetectable ever since) and CMP-014 (a register carried "Next review"
dates that no instrument, hook, or human ever read in its whole life).
v1 arrived at the same class as ADR-042, "check liveness".

**Mechanics sketch.** Two mechanical checks: (a) every guard names the
root that invokes it, and a sweep proves each guard reachable from a
live root — a deleted or orphaned guard goes red *by its absence from
the wiring*, not by anyone remembering it; (b) every register column
that encodes an obligation (a review date, a probation date) names its
reader, and a sweep fails on a reader-less column. The sweep adjudicates
its own complement: it states what it does not cover.

**Buyer class:** a guard found deleted/orphaned with nothing having
noticed, or an obligation column found reader-less past its date —
including this repository's own probation dates (gate-metrics.md's
named tension is one unattended date away from being this complaint).

**Refuses:** guarding prose intentions — only wired, executable guards
and dated obligation columns are in its population.

## F-11 — Decision propagation

**Origin: the falsifier clause, second finding (operator ruling,
2026-09-01).** CMP-016: a line deleted while reverting a dead design
was silently depended on by a later change, re-opening a push-boundary
bypass; its measured twin in v1: ADR-057 changed what `stale` means
and two dependent claims stayed live-and-false for two weeks — "no
mechanism runs decision → dependent claims."

**Mechanics sketch.** Decisions become watchable objects: a capsule
may watch a *decision record* (an ADR file, a ruling section) the same
way it watches code, so changing the decision suspects everything
standing on it; and a work item may declare the decision it stands on,
so `check` lists work items whose premise changed. The reverse of
F-5's tripwire: not "the evidence changed under the sentence" but "the
premise changed under the work".

**Buyer class:** a decision amended or reverted while dependent work
or claims silently kept standing on the old version, and somebody paid.

**Refuses:** semantic impact analysis (judging *how* the change
matters is human work); this only makes the dependency visible.

## F-12 — Work queue

**Origin: operator ruling, 2026-09-01** (the agentic-environment
taxonomy; precedent for ruling-added rows: F-8/F-9). Anchored evidence
already in the register: CMP-011's cost line — "kuchnie-lm8, the P1
lead-fidelity item, sat blocked by finished work and was absent from
`truth ready`."

**Mechanics sketch.** A ready list that is **derived, never
hand-maintained** (v1's roster lesson: a hand-kept reading order was
the one artifact nobody could see rot): computed at read time from
open complaints, probation dates coming due, SUSPECT capsules, and
promoted-but-unbought harvest events — each row naming what acting on
it would buy and roughly what it costs. A `tl2 ready` verb, someday.

**Buyer class:** an operator turn spent asking "what now", or work
found blocked invisibly behind finished work.

**Refuses:** being a plan. The queue orders what exists; priorities
stay with the memo and the operator; it never invents work.

**Measured inheritance map (2026-09-02 beads-vs-wk study, anchors in
the session record):** when F-12 grows past `tl2 ready`, it inherits
from beads the DELIVERY and the DECOUPLED STORE (memories injected at
SessionStart via `bd prime --hook-json` — the shipped QB-013 remedy;
a work store separate from the fact log, proven by the freeze: beads
kept writing after the ledger died) and from v1's wk- kernel the
SEMANTICS (premise-at-birth links; one premise-validity filter applied
uniformly over ANY tracker source, printing `HELD <id> broken
premises:` — beads alone cannot know a fact went stale; executable
acceptance oracles screened by allowlist; G12-grade human-only
terminal acts). The strongest single lesson cuts against prose again:
v1 *designed* a session digest and never shipped it — delivery
documented is not delivery. Known trap: the beads-seam precedence
(filing one native issue silently deposes the `bd ready` default).

## F-13 — Budget sense

**Origin: operator ruling, 2026-09-01** (same taxonomy). Anchored
evidence: 555 of 630 resolved stalings were false alarms (consumer,
tr-e1225a78); "half the supervisor's effort went to ledger
bookkeeping" (supervision retro 2026-07-16); ceremony costing a
multiple of the fix (v1's own IV&V verdict).

**Mechanics sketch.** Cost as a column: each mechanism's row counts
not only catches, false alarms and misses (C3) but the **agent turns
and operator rulings it consumed** — recorded at the events that
consume them, like everything else in gate-metrics. A monthly
ceremony-versus-product line makes the subscription's fate readable.

**Buyer class:** a month in which ceremony visibly ate the
subscription instead of the product, or a gate whose upkeep costs more
than its catches are worth.

**Refuses:** tracking humans' time — only countable repository events
(turns, rulings, verdict actions) enter the ledger.

## Not transplanted — priced absences

Deliberate refusals of DO-178-shaped machinery, each with its reason,
so a future reader knows they were weighed and declined rather than
forgotten (this section was lost once, in the first→second founding
rewrite, and restored by operator ruling of 2026-08-31):

- **Structural coverage / MC/DC** — a red-ocean tool category
  (coverage.py, commercial analyzers). Their *reports* may enter F-5
  capsules as evidence; rebuilding them is refused (scope R3).
- **Full DO-330 tool qualification** — constitution C2's two witnesses
  buy the premise (never trust an unchecked checker) at a price a
  business tool can carry; the full qualification regime has no buyer
  here.
- **Three requirement levels (system/HLR/LLR)** — business software
  carries two usefully: the spec sentence and its `SC-` assertions. A
  third level is ceremony at this weight.
- **SOI audits** — there is no certification authority; its role is
  played by C3 probation (gates die by their own record) and the
  operator's rulings.
- **Validation and process assurance** — scope R1 and R4.
- **Archive, retention, and backup** (DO-178C SCM's
  archive/retrieval/release concept) — not built; priced by operator
  ruling, 2026-09-01, after an external standards audit. The declared
  reliance is git remotes (the github origin). Named honestly: a
  repository whose entire value is "the record still corresponds"
  names loss of the record as its own worst hazard, and it declares
  this reliance instead of pricing a mechanism.
- **Service bulletins / airworthiness directives** — known-defect
  notification to pinned installations is manual and unguaranteed
  (declared in the release runbook, same audit). Measured once:
  installation #2 stayed pinned at v0.1.1 while a known mirror
  blindness (CMP-020) existed until v0.1.2; the mitigation happened
  by hand, exactly once.
- **Classic ADR corpus** (priced by operator ruling, 2026-09-01, after
  the absence was caught undeclared) — refused: v2 records decisions
  at their point of force — complaint dispositions, ruling lines,
  erratum sections, register rows, priced purchase records, `ret-`
  tombstones — and a parallel decision register would be a second
  register of the same items: the EPI-collision class, and the disease
  C1's own purchase record names ("~60 ADRs of machinery bottom-up").
  Accepted cost, named: decisions that are neither purchases nor
  document rulings live in commit messages — anchored, append-only,
  but not topically discoverable. When F-11 is bought, **ruling
  sections and dispositions — not new ADR files — are its watchable
  decision records**; and the first decision that proves
  undiscoverable in a commit message is the complaint that buys a
  decision index.

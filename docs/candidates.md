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

The eighth distrust — "the tool lied and we believed it" — is not a
candidate: it is constitution C2/C3, already law for every gate. The
first founding wrapped it as a feature to have something to call BUILT;
two reviews independently killed that.

## F-1 — Spec testability lint

**Transplants:** requirements analysis, the cheapest defect source in
IV&V (a requirements defect found at requirements costs 1×; at test,
10–50×; in production, 100×+).

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

**Refuses:** judging whether a requirement is the *right* requirement
(scope R1).

## F-2 — Bidirectional traceability mirror

**Transplants:** bidirectional traceability (DO-178C §6.4.4.3 doctrine,
IEEE 29148) at grep weight. Inherited from the v1 spec-coverage pilot —
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

**Transplants:** the one axis of IEEE 1012 independence an LLM can
actually supply: independence of **context**.

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

**Buyer class:** an author-verified claim later proven false — the
author's own confirmation was the failing control.

**Refuses:** claiming IEEE-1012 independence (organizational and
financial axes are structurally absent and declared so, not simulated).

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

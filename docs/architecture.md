# Architecture — engine, installations, and the one rule for LLMs

Status: **ACCEPTED** (operator ruling of 2026-08-31, after one
adversarial falsification round and two external reviews; recorded by
the agent on the operator's explicit instruction).

## Role of this document

This is the invariant layer: the shapes every mechanism must fit,
regardless of which complaint buys it. It contains no feature designs —
those live in `docs/candidates.md`, deliberately unratified. A sentence
here describes a constraint, not a mechanism's existence.

## 1. Two nouns

**Engine** — the verifier code. Stateless: it holds no store between
invocations, remembers no repository, and phones no home. It is
distributed as tagged releases only.

**Installation** — a copy of the engine's client-tier tools plus local
state, living inside the repository it verifies. All state in this
system is installation state (scope R5). Two installations share
nothing and can never collide: each receives its own identifier prefix
from `docs/registers/prefixes.md` at initialization (constitution C5).

This repository carries one installation of its own (since CMP-002
bought the first client-tier mechanism), one of many and with no
privilege: it reaches the engine only through the public surface every
client installation gets (constitution C4).

## 2. State model: recompute over record

The rule that keeps this system light, learned at cost in v1:

> A fact that is cheap to recompute from zero is recomputed at read
> time, never stored. State exists only for what recomputation cannot
> give back.

Only three kinds of record qualify, and they are the whole state model:

| Store (per installation) | Contents | Why it cannot be recomputed |
|---|---|---|
| `capsules.jsonl` (append-only) | evidence capsules: sentence, command, output hash, commit anchor, watched paths | it records a *past execution*; re-running produces today's output, not the recorded one — comparing the two is the product |
| `gate-metrics.md` | per-gate catches, false alarms, probation dates | it records *events witnessed by people* |
| `complaints/`, manifests, the prefix rows | harm records and allocation acts | a name or a ruling is a *decision*, not a derivation |

Everything else is a projection computed at read time from these stores
plus git. In particular **suspect status is not stored**: a capsule is
suspect iff `git` shows any of its watched paths changed since its
anchor. v1 stored suspicion as events; v2 computes it, because git
already holds the answer.

Three failure modes of this projection were named at ratification so
nobody discovers them as surprises; a fourth was added by dated
erratum (see mode 4):

1. **Unreachable anchor.** After a history rewrite (rebase, force-push,
   aggressive GC) the anchor commit may not resolve. The disposition is
   fail-closed: **an unresolvable anchor makes the capsule suspect**,
   never silently fine.
2. **Capsule integrity.** "Append-only" on `capsules.jsonl` is a
   declared intention with no mechanism: a hand-edited hash or a
   narrowed watched-paths list would make future rechecks pass. Until a
   complaint buys an integrity check, this sentence is the honest
   record of that gap.
3. **Watched-set adequacy.** The watched paths are chosen by the
   capsule's author; a sentence invalidated by a file *outside* its
   watched set is never marked suspect, by design. Adequacy of the set
   is the author's responsibility and is not verified by the engine.
   The extreme case is time itself: a sentence can be invalidated by
   nothing in the repository — an external dependency moved, the world
   drifted — and no watched set can see that. v1 carried read-time TTL
   for exactly this channel and also measured its cost (inert expiry
   records, ceremony); v2 declines it until a complaint buys it, and
   until then this sentence is the honest record of that channel.
4. **Engine-version semantics.** *(Erratum addition — operator ruling
   of 2026-09-01, delegated via "Zlec subagentowi", after an external
   standards audit.)* A capsule does not record the engine version
   that produced it, so what a check *means* can drift across engine
   versions — the CMP-020 class: `mirror`'s citation semantics changed
   between v0.1.1 and v0.1.2, and no capsule can say which semantics
   blessed it. Declared until a complaint buys the field; until then
   this sentence is the honest record of that gap.

## 3. Public surface

One CLI entry point operating on flat files, communicating by exit
codes and plain text. Client-tier tools are dependency-free (Python
stdlib only), run no daemon, open no network connection of their own,
and read nothing outside the repository they are installed in. One
honest qualification: a capsule recheck executes the *author's*
recorded command, and the engine cannot guarantee that command touches
no network — the no-network property holds for the engine's own code,
not for what an author capsules. The engine-dev tier may carry
development dependencies; they never install.

The CLI is `scripts/tl2`; its verb set grows only with purchases —
first two verbs: `capsule` and `check` (CMP-002). The name was decided
at the first client-tier purchase, not before: naming an unbuilt
surface is how v1 grew documentation ahead of truth.

## 4. Gate tiers and the separation proof

Every executable check is labeled at birth (constitution C6):

- **`client`** — ships to installations; minimal; scoped to the push
  that triggers it (a docs-only change must not pay for a full battery).
- **`engine-dev`** — polices this repository's own development; never
  installs.

The boundary is falsifiable since 2026-09-01:
`scripts/separation-canary` (first F-7 instance, bought by CMP-010)
installs the client tier into a sandbox, runs every verb that exists
at run time, and reds on any access outside it — three independent
detectors (audit hook, mtime sweep, status diff), with the subprocess
read limit declared in its header. It is invoked manually before
release tagging; nothing automates that yet, and this sentence is the
honest record of the remaining gap.

## 5. Version boundary

Client installations pin tagged releases. Engine development runs on
HEAD, where breakage is welcome. An installation never reads a file
outside its own repository — the same property candidate F-7 proves.

## 6. The LLM rule

> **An LLM proposes; a mechanism or a human disposes.**

Consequences, binding on every candidate in `docs/candidates.md`:

1. No LLM output ever gates: it never computes a status, never blocks a
   commit or push, never writes a verdict a machine acts on.
2. Every LLM output lands as a reviewable artifact marked
   `proposed-by: llm`, carrying the model identity and the prompt that
   produced it, and stays a proposal until a human accepts it or a
   mechanical check subsumes it.
3. Rationale: the first premise is transplanted from DO-330 — a tool
   whose output you trust without checking requires qualification.
   That an LLM cannot be qualified is this repository's inference
   `[I]`, not DO-330's sentence — warrant: DO-330 qualification
   presumes a deterministic tool with bounded behavior, and an LLM's
   output distribution satisfies neither premise. Elided condition,
   restored: DO-330 requires qualification only when a tool's output
   is used to *eliminate* other verification — which is exactly the
   use this rule forbids. Therefore an LLM output is never trusted
   without checking.
4. Declared limit of LLM review: two instances of the same model are
   independent in **context**, not in **failure** — a fresh reviewer
   inherits none of the author's rationalizations but shares the author
   model's blind spots. Every LLM reviewer report must state this limit
   in its header. This repository's own founding measured the limit: a
   same-model adversary found fifteen findings and missed the three
   best ones, which arrived from differently-contexted external
   reviewers.

Honesty about enforcement, owed to CMP-001 (a prose rule demonstrably
does not bind an agent at the moment of acting): consequences 1–4 are
**declared intentions** until gates are bought for them. Only one part
is mechanically checkable today — the *presence* of the marker and
limit header on artifacts that carry them; an agent that omits the
marker is undetectable by machine. Any candidate shipped to clients
whose guarantee rests on this rule must disclose exactly that to the
buyer. Until a complaint buys better, this sentence is the honest
record of that gap.

This rule is how scope R2 ("no judgment-shaped checks") and the use of
LLMs coexist: the judgment never enters the gate; it stops one step
before, where a person or a deterministic check can see it.

## 7. What this architecture refuses

Pointers, not repetition — the refusals live in `docs/scope.md`: no
validation (R1), no judgment inside gates (R2, enforced here by §6), no
rebuilt coverage or static analysis (R3 — their outputs enter capsules
as evidence), no process assurance (R4), no engine-side state (R5,
enforced here by §2).

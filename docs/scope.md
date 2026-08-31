# Scope

Status: **ACCEPTED** (drafted by an agent from the operator's recorded
lessons of truth-ledger v1; ruled on by the operator). A boundary
cannot be measured from inside; it has to be declared, and declaring it
is the operator's act, not an agent's.

Ruling: ACCEPTED — operator ruling of 2026-08-31, recorded by the
agent on the operator's explicit instruction.

## The sentence this system is built on

> Program testing can be used to show the presence of bugs, but never to
> show their absence. — Dijkstra, 1969

## What this is

An apparatus that answers **one** question, commercially, for business
software whose failure does not endanger life or health:

> Does a written sentence still correspond to the repository it describes?

In ISO/IEC/IEEE 12207 terms it sits **below** the baseline. It is
verification, not validation. How it is constructed — the engine and
its installations — is design, not boundary, and lives in
`docs/architecture.md`.

## Refusals

These five sentences are the floor every future "no" stands on. Each
one exists because its absence was measured, at cost, in truth-ledger v1.

**R1 — No validation.** This system will never judge whether a sentence
is about the right thing, whether the work was worth doing, or whether
the product is the right product. That judgment belongs to people.

**R2 — No judgment-shaped checks.** Every check this system ships is
mechanical, deterministic, and cheap to recompute from zero. A check
that requires opinion, taste, or an expensive re-verification does not
enter the engine; it stays with humans, or it does not exist here.

**R3 — No competition with coverage and static-analysis tools.** Their
outputs may enter capsules as evidence. Rebuilding them is refused.

**R4 — No process assurance.** Auditing whether a team followed its
process is consulting, not this product.

**R5 — The engine holds no state.** All state — claims, manifests, gate
metrics — lives inside the installation that produced it. A client's
evidence never leaves the client's repository.

## The declared ceiling

truth-ledger v1's most valuable self-measurement, adopted here as a
disclosure: catches in this class of apparatus concern **form** —
correspondence, presence, staleness of sentences — never the substance
of the work the sentences describe. The measurement lives in v1's
catch-log records and is cited here unverified (AGENTS.md rule 8).
Nothing this system will ever ship can say the work was good — only
that the record of it still corresponds.

## What "in scope" means operationally

A question of the form "is X in scope?" is answered by this file, not by
discussion. If this file does not answer it, the answer is **no** until
an operator ruling amends this file. Amending this file is itself an
operator act, recorded with a date.

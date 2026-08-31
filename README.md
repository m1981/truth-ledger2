# truth-ledger2

A commercial verification engine for business software. It answers one
question:

> Does a written sentence still correspond to the repository it
> describes?

Verification, not validation — it will never tell you a sentence is
about the wrong thing, and it checks **form, never substance** (the
ceiling is declared in `docs/scope.md`). See `docs/scope.md` for the
five refusals that define the product; they are the product.

## Architecture in one paragraph

An **engine** (stateless verifier code) and its **installations** (a
copy of the tools plus local state, living inside the repository it
verifies). This repository is installation #1: since CMP-002 bought
`scripts/tl2` (the first client-tier mechanism), it dogfoods the engine
through the same public surface a client installation gets — no private
doors. The installation's state is `capsules.jsonl`.

## Current state

Founding documents plus one mechanism, which entered by the book:
CMP-001 (the founding agent broke its own English-only rule within
minutes) bought `scripts/githooks/commit-msg`, witnessed red on a
seeded fault and tested green against a corpus of plausible English
messages before it was allowed to block. Candidate features live in
`docs/candidates.md` — deliberately never ratified, activated only
through complaints (constitution C1).

## Read order

1. `docs/scope.md` — what this refuses to be (5 refusals) and its
   declared ceiling
2. `docs/governance/constitution.md` — how anything enters (6 rules,
   each priced by a named failure)
3. `docs/architecture.md` — engine, installations, the LLM rule
4. `docs/candidates.md` — designed candidates, none of them promises
5. `docs/market-memo.md` — why anyone would pay (non-normative)
6. `docs/registers/prefixes.md` — identifier allocation
7. `docs/complaints/README.md` — the door mechanisms enter through
8. `AGENTS.md` — conduct for agents working here

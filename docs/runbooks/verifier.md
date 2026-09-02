# Runbook: the fresh-context verifier (F-4)

A fresh session supplies the *rationale* of IEEE 1012 technical
independence — a fresh viewpoint — while supplying none of 1012's
three axes (technical, managerial, financial): in 1012's frame it is
the same tool. What it buys is independence of **context** — never of
failure (architecture §6.4; this founding measured a same-model
adversary missing the three best findings). The economics are v1's:
98.5% empty "agree", 1.5% hit rate overall `[unverified here — v1
records]` — so dispatch is the exception, chosen by criteria, never
the routine.

## When to dispatch — the more of these hold, the higher the expected value

1. **Self-certification** — the author verified their own work (every
   measured verifier catch in v1 was this class).
2. **Not mechanically recomputable** — a deterministic command settles
   it? Then recompute (scope R2); the verifier is for
   judgment-above-recipe: "the gate is *invoked*, not just named",
   "the fix reaches all three variants", "the number means what it
   says".
3. **Load-bearing destination** — the sentence enters law, a purchase
   record, a release, or a client-facing surface (CMP-003's day~200 is
   the canonical case).
4. **Asymmetric cost** — wrong-and-believed costs more than the
   ceremony.

**Anti-dispatch** (measured waste): a fresh claim minutes after the
author's own green run; anything recomputable; volume verification —
capsules and `check` cover those.

## How

1. **Brief** — `./scripts/tl2 verify --brief <cap-id>`; hand the
   output verbatim to a fresh session that inherits nothing from the
   author. Staffing per AGENTS rule 9: a fresh same-model session is
   the floor; a differently-contexted reviewer is the standard.
   *Done when:* the brief is delivered with no author context attached.
2. **The verifier works beyond the recipe** — the brief's three
   duties; a verifier that only re-runs the hash is a recompute, which
   needed no verifier.
3. **Intake** — `./scripts/tl2 verify --intake <report-file>`; the
   only gating step: marker, limit line, valid verdict, or refused.
   *Done when:* intake prints "report accepted".
4. **File the report** — `docs/verifications/<cap-id>-<date>.md`,
   committed; the report is an artifact, never a status.
   *Done when:* the file is in the tree.
5. **The human disposes** — the operator reads the verdict and acts or
   declines; the verdict itself changes nothing mechanically.
   *Done when:* the disposition (action taken, or none) is stated in
   the session's decision package.

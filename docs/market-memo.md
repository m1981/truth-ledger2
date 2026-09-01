# Market memo — why anyone would pay for this

Status: **NON-NORMATIVE.** This memo steers the operator's attention;
it never justifies a purchase. A mechanism enters only through a filed
complaint (constitution C1) — citing this memo buys nothing, and a
disposition that leans on it instead of on a harm event is invalid.
It is the third genre in this repository: scope and constitution are
law, candidates are reasoning, this is direction. Direction can be
wrong without anything being broken; revise it by operator ruling,
dated.

## The selection principle, in one sentence

Ship only checks that are mechanical and deterministic, cheap to
recompute from zero, and quiet on legitimate traffic — everything
judgment-shaped or expensive stays with humans or is refused (this is
scope R2 + constitution C2/C3 read as one sentence; it came from the
measured IV&V verdict on v1: *the mechanical part is stronger than the
independent-agent part*).

## Position: what is actually new here

Almost every mechanism in this system has a 15–70 year pedigree
(in-toto/SLSA provenance, DOORS suspect links, fault seeding, event
sourcing, alarm rationalization). The pedigree analysis of v1
identified exactly one genuinely new thing: **suspect-links over
sentences produced by LLM agents** — candidate F-5's territory. Nobody
applied configuration-audit discipline to *what a model claims about a
repository*. In the era of agent-written code, the failure mode "a
confident, stale assertion with no record of how it was produced" only
grows. F-5 is the market position; everything else is the credible
apparatus around it.

**The backbone** is candidate F-2 (bidirectional traceability): the
cheapest to build, proven shape, and the thing a buyer can understand
in one demo. F-5 differentiates; F-2 carries.

**The second differentiator** is candidate F-8 (whisper): pushing
"these sentences watch the file you are about to touch" into the
agent's context at the moment of action — a mechanism no standard
conceives, because standards never had an actor whose attention is
programmable. Its natural sales channel is integration with agent
harnesses (hooks), which is also where the buyers of vector 1 already
live.

## The measured order (correction of 2026-09-01)

This memo originally implied F-2 → F-1 as the build order. The harvest
of 45 anchored harm events from v1 and its consumer says otherwise:
**F-3 dominates (14 events)** — tests, oracles and sentinels that
proved nothing — with F-4/F-5 next, and F-6 carrying the
best-measured single number in either repository: **555 of 630
resolved stalings were false alarms (worse than 3:1)**, and one
sentinel family produced 43 alarms with zero caught defects. F-1, the
memo's "cheapest finds", has the thinnest file (2 events). The
consumer also independently invented both the complaint register
(question-bank + incident-to-gap ritual) and the whisper-shaped
remedy (rule injection by SessionStart hook) — double validation of
the product's shape by its only real user so far. Direction follows
measurement: F-3 and F-6 lead, F-8 rides the consumer's own remedy,
F-1 waits.

## Who pays — two vectors

1. **Teams working with AI agents.** Docs↔code drift is a common,
   named pain today; verification of what agents assert and leave in
   documentation hits it directly. Their harm events are the natural
   source of early complaints.
2. **Compliance** (SOC 2, ISO 27001, GDPR audits) — the business-world
   analog of airworthiness certification: the company must *show
   evidence* that controls work. Audit-ready evidence — capsules with
   command, hash, and commit anchor, reproducible on an auditor's
   demand — replaces what is today assembled by hand in pre-audit
   panic. This is the vector with money already allocated to the
   problem.

## The operating model — operator, agents, a subscription

`[I]` unless marked. Three parties: an **operator** who rules,
countersigns and pays; **agents** who do everything reversible and die
with their sessions; a **subscription** — fixed monthly capacity, not
per-task billing. What this implies:

- **Motivation does not live in the agent** (it has no memory, no
  stake, no continuity). The project's motivation is structural:
  **pain** (the complaint register), **direction** (this memo),
  **rulings** (the operator), and a **queue** (candidate F-12) that
  answers "what is ready" between the operator's turns.
- **Instead of a plan: direction plus queue.** A ratified plan is an
  attractor that agents execute literally after reality has invalidated
  it — this repository's first founding measured exactly that and
  replaced its plan with a never-ratified catalog.
- **The operator is the scarcest resource.** Rulings are batched with
  evidence and a recommendation (AGENTS.md rule 10); nothing waits on
  the operator that is not genuinely theirs. `[M]` v1 carried
  "human-only" items that hung for weeks.
- **Rulingless windows are work.** The subscription flows when nobody
  is issuing commands; those windows belong to harvests, sweeps, and
  capsule maintenance — never to new mechanisms (C1 still holds).
- **The sensorium, as vocabulary:** correspondence (`check`), touch
  (`whisper` — "you are about to touch this"), proprioception
  (gate-metrics and F-10 — feeling one's own organs), and two senses
  known to be missing: time and the external world (architecture §2
  mode 3), and budget (candidate F-13). `[M]` for the cost of the
  missing budget sense: 555 of 630 stalings were false alarms, and
  half a supervisor's effort once went to ledger bookkeeping.

## The sales boundary

The declared ceiling (scope) is also the honest limit of every pitch:
this apparatus checks that **records still correspond** — it will never
say the work was good, the product right, or the process followed.
A sale that promises more sells something this system refuses to be.

## Bridge to reality

A harm event from a client or pilot engagement is a first-class
complaint (complaints register). That is the only door market demand
has into this repository — and it is the same door everything else
uses.

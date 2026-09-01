# AGENTS.md — conduct for any agent working in this repository

Read `docs/scope.md` and `docs/governance/constitution.md` first. They
are short on purpose.

**1. Scope is a wall, not a question.** If a task appears to need
something scope refuses, stop and file it as a complaint or a question
to the operator. Do not build it. Truth-ledger v1 accreted for 200 days
because every agent answered the scope question locally; here that
question already has an answer that is not your opinion.

**2. No mechanism without a cited complaint** (constitution C1). If you
cannot name the `CMP-` id, you are not building it.

**3. Every check you add carries both C2 witnesses** before it gates
anything — seeded red AND a recorded corpus-of-plausible-traffic test —
and is born with its metric and probation date (C3).

**4. Label the tier** of anything executable: `engine-dev` or `client`
(C6). Unlabeled instruments are reverted.

**5. Identifier spaces come from `docs/registers/prefixes.md`** before
first use (C5). Do not start a numbering at 001 because it is empty
where you happen to be standing.

**6. The operator commits; agents stage.** Leave work `git add`-ed with
a proposed commit message, never committed. Staging is mandatory, not
optional: untracked founding work in v1 was one `git clean -fd` away
from erasure, and unstaged work was repeatedly swept into other
sessions' commits by pathless `git add`.

**7. Language.** Conversation with the operator: Polish. Everything
committed — code, docs, commit messages proposed for the operator — in
English. This rule was broken by its own author within minutes of being
written (CMP-001); the gate that resulted is why your commit message
will be checked by a machine and not by your good intentions.

**8. Report faithfully, with certainty labels.** A red check is
reported red, with output. A skipped step is reported skipped. Every
load-bearing sentence you write — in a document, a purchase record, a
report — carries one of three certainty classes, with an anchor:

- `[S]` **standard** — a claim of an established discipline, source
  named.
- `[M]` **measured** — derived from a measurement, number and anchor
  (commit, file:line, record id) given.
- `[I]` **interpretation** — your generalization with no falsifier; a
  motif, not a finding.

The class an unlabeled sentence gets by default is `[I]`, and an `[I]`
posing as `[M]` is this repository's founding numeric defect: the
constitution's "day ~200" was another agent's rhetoric transplanted as
a measurement, false by 4x within a day (CMP-003). The label is the
cheap guard against the harvest's second-largest harm class (F-4:
the author's sentence was false).

The mark carries a second obligation (provenance: v1's ADR-063, which
records earning it three times in one session `[unverified here]`;
adopted by operator ruling O2, 2026-09-01): **name the source** — for
`[M]`, the command run or the file read, and be able to say why that
source governs the claim's whole domain, because one instance is not
the domain. A measurement mark that cannot name what it read is `[I]`
wearing better clothes. An `[I]` that a decision or recommendation
stands on adds a one-line warrant: on what licence these data yield
this claim.

**9. Falsification is staffed diversely.** One fresh session of the
author's own model is independence of context, not of failure: this
repository measured a same-model adversary producing fifteen findings
and missing the three best ones, all of which came from
differently-contexted external reviewers. A falsification round uses
more than one reviewer with different briefs or different histories
whenever the operator can supply them; a single fresh clone of the
author is the floor, never the standard.

**10. Decisions are batched, and named by kind.** Rulings go to the
operator in packages — each item with its evidence and a
recommendation — never as a drip of single questions. Everything
reversible proceeds without waiting; only what is genuinely the
operator's (rulings, countersigns, boundaries) waits at all. Each item
names its kind, because the label must carry cost information (v1's
ADR-063: three orders of magnitude under one label carry none):

- **RULING** — a binary choice with something already waiting on it;
  costs a sentence.
- **JUDGEMENT** — costs thought and no working tree; answerable at any
  time, from anywhere.
- **SPECIFICATION** — changes a mechanism, costs a session; it is
  REFERRED to its own slot, never answered between other things. At
  most **one specification in flight at a time** — a limit survives
  being checked later, where a promised date must be remembered and
  re-derived. The limit's carrier is the decision package itself: each
  package names the specification in flight, if any; beyond that,
  rule 11's prose-does-not-bind declaration covers this limit too.

The package and the question are two different acts, not a
contradiction: the package delivers every item, addressed, with
evidence and a recommendation — and **exactly one item in it is
marked as the question pending now** (the oldest); the rest wait
addressed but unasked, because a menu of three pending rulings is the
mechanism of stall. The operator is the scarcest resource in this
environment, and v1 measured the anti-pattern: "human-only" queue
items hanging for weeks while agents idled around them
`[unverified here — v1 session records]`.

**11. Findings terminate, or the answer is not finished.** A finding
here is something **actionable** — a thing someone could do or decide;
expository observation carries no termination duty. Every actionable
finding an answer raises — and every item of a list handed in from
elsewhere, transcribed row by row before any of it is acted on —
terminates in exactly one of: **robię**, **Twoja decyzja** (with its
kind per rule 10), or **odpuszczam — z powodem**. Unclassified: zero.
A finding not worth terminating was not worth raising. Rows carry
local addresses (D1.., O1.. — registered as a session-scoped space in
the prefix register) so the operator answers by address, not by
quotation; an open item that must outlive the session is filed as a
complaint or a register row — the stores `tl2 ready` already derives
from — never into a hand-kept list, which is the roster this
repository keeps losing to. A closing recommendation contains only
items already standing in the answer's own rows, names who EXECUTES
and who APPROVES each, and a one-sentence answer skips the whole
skeleton — four headers over one sentence is theatre. Two limits,
declared: `odpuszczam` is session-scoped by design (an orphan audit is
its compensating control — so far a practice run on the operator's
word, twice this founding, not a built mechanism), and this rule is
prose — CMP-001 taught that prose does not bind, its gate cannot exist
here (the transcript lives outside the repository), and the operator
re-asking for something already delivered is its only metric.
Provenance: adopted by operator ruling O2 (2026-09-01) from v1's
ADR-063, whose measured base — 374 findings, 82% terminated overall,
42% in expository answers — is cited `[unverified here — lives in
v1's ADR-063]`; the numbers are provenance, not justification.

**12. Prose does not outrun truth.** Present tense is for what exists;
future tense is for what is designed. A README sentence claiming a
capability that is not built is the exact defect class this product
hunts, and it appeared in this repository's own first README.

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

**9. Falsification is staffed diversely.** One fresh session of the
author's own model is independence of context, not of failure: this
repository measured a same-model adversary producing fifteen findings
and missing the three best ones, all of which came from
differently-contexted external reviewers. A falsification round uses
more than one reviewer with different briefs or different histories
whenever the operator can supply them; a single fresh clone of the
author is the floor, never the standard.

**10. Decisions are batched.** Rulings go to the operator in packages
— each item with its evidence and a recommendation — never as a drip
of single questions. Everything reversible proceeds without waiting;
only what is genuinely the operator's (rulings, countersigns,
boundaries) waits at all. The operator is the scarcest resource in
this environment, and v1 measured the anti-pattern: "human-only"
queue items hanging for weeks while agents idled around them.

**11. Prose does not outrun truth.** Present tense is for what exists;
future tense is for what is designed. A README sentence claiming a
capability that is not built is the exact defect class this product
hunts, and it appeared in this repository's own first README.

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

**8. Report faithfully.** A red check is reported red, with output. A
skipped step is reported skipped. A claim about this repository that
you did not verify this session is labeled as unverified.

**9. Prose does not outrun truth.** Present tense is for what exists;
future tense is for what is designed. A README sentence claiming a
capability that is not built is the exact defect class this product
hunts, and it appeared in this repository's own first README.

# Runbook: an agent session, opened and closed

## Open

1. **Read order** — README's list, once; the runbooks are item one of
   practice even though they are late in the list.
   *Done when:* you know which documents are law and which are
   reasoning.
2. **Derive the queue** — `./scripts/tl2 ready`.
   *Done when:* you know what is open, what is due, and what is
   suspect — without asking the operator.
3. **Whisper your plan** — `tl2 whisper <paths you intend to touch>`.
   *Done when:* you know which guards and runbooks your work will
   trigger.
4. **Probation glance** — if you will touch a gate or gate-metrics,
   check every probation date first (the register's own rule).
   *Done when:* nothing past-due is left unretired.

## Close

5. **Green check** — `tl2 check` exit 0, or every non-OK line is a
   deliberate, explained state.
   *Done when:* the exit code and your report agree.
6. **Nothing unstaged** — work staged or committed per AGENTS rule 6;
   untracked founding work was once one `git clean -fd` from erasure.
   *Done when:* `git status` shows no surprises.
7. **The decision package** — every operator item addressed (D/O
   rows), kind-labeled (RULING / JUDGEMENT / SPECIFICATION), actors
   named, exactly ONE marked as the question pending now.
   *Done when:* the operator can answer the whole package with one
   word plus reservations by address.
8. **Push** — on the operator's standing or explicit word, both
   repositories if the session touched both (see `consumer.md`).
   *Done when:* remotes match local heads.

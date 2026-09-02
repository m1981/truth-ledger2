# Runbooks — choreographies, as checklists

Processes are the category the document layers were missing: not law,
not reasoning, not direction, not state — **ordered, repeatable
sequences with verification points**. Provenance `[S]`: SOP/runbook
practice, ISO 9001 documented procedures, and Kotarbiński's
praxeology; from DO-178, the plans-define-processes inheritance; the
checklist FORM is aviation-operational practice (normal/non-normal
checklists — Gawande's tradition), not the SDP.

Form rules, priced by measurement:

- **Checklist, never narrative** — every step ends in "done when", a
  condition someone can check. v1's process document
  (`session-close.sh`) decayed into "prose no code invokes"
  `[M — v1 pre-push-checks.sh header]`; narratives rot fastest.
- **Delivered at the moment of action, not in a reading order** — the
  QB-011 lesson: a bank entry is read when someone opens the bank; the
  failure happens mid-command. Delivery channels: the read order
  points here once; each runbook is capsule-guarded, so `tl2 whisper`
  names it before you touch what it choreographs; kuchnie's
  SessionStart injection carries the consumer contract.
- **Guarded against rot** — each runbook's capsule watches the files
  its process touches: change the mechanics, and the runbook goes
  SUSPECT before anyone executes a stale process.

| Runbook | Choreographs |
|---|---|
| `purchase.md` | complaint → mechanism, the full C1→C2→C3 cycle |
| `maintenance-loop.md` | editing a capsule-watched source |
| `session.md` | opening and closing an agent session |
| `consumer.md` | the two-repository contract of an installation |
| `release.md` | tagging the engine |
| `verifier.md` | dispatching a fresh-context verifier and intaking its report |

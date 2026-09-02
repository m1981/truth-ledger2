# F-12 kernel shape — the premise-validity filter (2026-09-02)

Authorized by: operator ruling of 2026-09-02 (growth of F-12 past
`tl2 ready`, as a CMP-018 extension). Precedent for ruling-driven
growth: F-8/F-9/F-12 rows themselves [S: docs/candidates.md, F-12
origin line].

## What the kernel is NOW

1. **tl2 stays the premise-validity filter, never the tracker** [S:
   candidates F-12, measured inheritance map]. A work item is a record
   naming its premises — capsule ids, the facts this engine already
   pins. The filter is one pure function over (item id, premise list)
   plus the capsule store's read-time projections; it applies
   uniformly to ANY item source (wk-'s join_ready lesson [S:
   candidates F-12]). Only one source is wired now: a minimal native
   store, `work.jsonl` — decoupled from the fact log per the beads
   freeze lesson [S: candidates F-12], append-only like
   `capsules.jsonl` (an item is an intent record, not recomputable;
   its READY/HELD status is never stored — recompute over record [S:
   architecture §2]).
2. **Verbs**: `tl2 work "<title>" --premises <cap-id>...` files an
   item (`wk-<hex8>` content-hash id — row added to
   docs/registers/prefixes.md before first use, C5); `tl2 work --done
   <wk-id>` appends a closing record. `tl2 ready` gains work rows:
   all premises OK (or absent) => `work ready <wk-id> — <title>`;
   otherwise `HELD <wk-id> broken premises: <cap-id> (<why>)...` —
   fail-closed, premises named. Ready stays advisory, exit 0 [S:
   mechanisms.md, ready entry].
3. **Fail-closed cases**: premise SUSPECT or STALE => HELD; unknown
   premise id => HELD (validation lives in the FILTER, not at filing,
   so an external source gets the same guard as the native store).
4. **Retracted premise**: retracted WITH successor => the filter
   substitutes the successor (transitively, cycle-guarded) and judges
   its status. Justification: a successor is by runbook definition
   "the same sentence updated to the new truth" [S:
   runbooks/maintenance-loop.md step 3], so the premise's identity
   survives re-anchoring; HELD-on-every-loop would recreate the
   CMP-015 ceremony-churn class [S: candidates F-5, authoring
   doctrine]. Retracted WITHOUT successor, or a chain that breaks or
   cycles => HELD, premise named — the claim is genuinely gone.

## Deferred (each awaits its own complaint, C1)

Delivery by harness injection (SessionStart/pre-edit) — a hook, the
whisper-gap precedent [S: mechanisms.md, F-8 declared gap]; external
tracker adapters (beads seam and its precedence trap); executable
acceptance oracles; priority/cost columns (F-13's business); item
editing beyond file/close.

## Red witness (vacuity doctrine: acceptance seen red pre-change)

[M — `python3 scripts/test-f12-kernel` run against `scripts/tl2` at
b129df9 (pre-change tree), 2026-09-02; verbatim, wrapped only]:

    S1 FAIL: not listed ready (filing failed: usage: tl2 [-h]
      [--store STORE] {capsule,check,vacuity,whisper,retract,mirror,
      ready,verify,lint} ... tl2: error: argument verb: invalid
      choice: 'work' (choose from 'capsule', 'check', 'vacuity',
      'whisper', 'retract', 'mirror', 'ready', 'verify', 'lint'))
    S2 FAIL: no HELD line naming the SUSPECT premise
    S3 FAIL: no HELD line naming the STALE premise
    S4 FAIL: unknown premise not HELD fail-closed
    S5 FAIL: retracted-with-successor item not ready, or
      retracted-no-successor item not HELD
    S6 FAIL: no-premise item not listed ready
    S6r PASS: complaint and probation rows unchanged, exit 0
    test-f12-kernel: 1 passed, 6 failed — RED
    SUITE_EXIT=1

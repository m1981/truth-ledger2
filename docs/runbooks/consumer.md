# Runbook: a consumer-installation session — the two-repository contract

An installation session serves TWO repositories: the consumer repo it
works in, and the engine upstream (`truth-ledger2`). Neither is
optional. The contract's proof-of-value: installation #2's first hour
measured 28 false alarms and bought the slug-scoping fix upstream the
same hour `[M — gate-metrics, mirror row]`.

1. **Harms flow upstream** — a harm event here is a first-class
   complaint there ("whose harm qualifies: anyone's"); file the CMP in
   the engine repo, anchored to this repo's commits.
   *Done when:* the CMP exists upstream with a dated anchor into this
   repository.
2. **Engine defects are fixed upstream, never patched locally** — the
   vendor copy is never edited in place (C4: one public surface);
   the fix lands in the engine with both witnesses, then ships as a
   tag.
   *Done when:* the engine has a new tag and the fix's metric row.
3. **Re-pin** — copy the client CLI from the new tag; update the
   installations table in the engine's prefix register.
   *Done when:* `scripts/tl2` here matches the tag and the register
   row names it.
4. **Push BOTH before closing** — the consumer repo through its own
   battery, the engine with `--follow-tags`.
   *Done when:* both remotes match both local heads.

## kuchnie-specific

5. **The freeze is law** — `.truth/FROZEN.md`; nothing writes to the
   v1 ledger (a guard capsule pins its record count); G12 acts are the
   operator's own terminal, never an agent's.
6. **The battery is real** — every push runs ~1,450 tests plus the
   golden; a red there is a finding, not an obstacle.
7. **deps-graph tax** — adding tracked files stales
   `docs/deps-graph.jsonl`; run `scripts/deps-graph.py --build` as the
   LAST step before the commit that adds files `[M — this tax was
   paid twice on 2026-09-01]`.

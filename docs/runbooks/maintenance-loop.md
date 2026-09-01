# Runbook: guard maintenance loop (a watched source is being edited)

1. **Whisper first** — `tl2 whisper <paths>` before touching anything.
   *Done when:* you can name every guard your edit will suspect.
2. **Edit, then commit the edit** — successors must anchor at a commit
   that already contains the change.
   *Done when:* the working tree is clean.
3. **File successors first** — one per outdated guard, same sentence
   updated to the new truth; take each id from the `filed cap-…`
   output line.
   *Done when:* every successor shows OK in `tl2 check`.
4. **Retract the outdated generation** — ids taken from the CURRENT
   `tl2 check` output (the SUSPECT lines), **never from memory**:
   memory once supplied a generation two loops stale, the first
   retract refused, the chain broke, and a false commit message
   shipped `[M — TL2 commit 5590c08, the correction record]`.
   *Done when:* each retract prints `-> <successor id>` (the link is
   mandatory; four unlinked tombstones from the one loop run in the
   wrong order are the counter-example).
5. **Close** — `tl2 check` exit 0 with RETRACT lines readable as
   history; commit `capsules.jsonl`; push per session runbook.
   *Done when:* check is green and the store is committed.

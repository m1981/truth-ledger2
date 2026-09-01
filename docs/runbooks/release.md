# Runbook: an engine release (tagging)

1. **Separation canary** — `./scripts/separation-canary`.
   *Done when:* exit 0 ("green — engine repository untouched").
2. **Green store** — `tl2 check` exit 0; probation dates swept
   (anything past-due retired by its record first).
   *Done when:* both hold.
3. **Tag** — annotated, `vX.Y.Z`, message naming what the release
   carries and which complaint bought it.
   *Done when:* `git tag -n1 vX.Y.Z` reads true.
4. **Push with the tag** — `git push --follow-tags`.
   *Done when:* the remote lists the tag.
5. **Re-pin installations** — for each row in the installations table,
   run `consumer.md` steps 3–4, or record explicitly why an
   installation stays on the older tag.
   *Done when:* every installations-table row names either the new tag
   or a dated reason.

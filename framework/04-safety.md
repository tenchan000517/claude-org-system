# Safety

The rules that let the system change itself without breaking. These apply to *any* structural change
(standing up the secretary, migrating memory, denoising, adopting a new piece).

## The non-negotiables

1. **Back up before you change.** Copy the target to a timestamped backup *and confirm the backup* before
   any destructive or moving operation.
2. **Stay in scope.** Touch only what the current step names. Never wander into other directories/files.
3. **Add and move; don't delete.** Prefer additive changes and relocations over deletions. When you do
   delete, it must be reversible from the backup.
4. **Protect the assets.** Never gut working-rule/feedback memory or existing tooling. They're functions.
5. **When in doubt, leave it.** Ambiguity defaults to no-change — *for irreversible actions*. (For
   reversible ones, decisiveness is fine; see below.)
6. **Report what changed and how to undo it,** in one line, every time.

## Safety = reversibility, not paralysis

A system made "safe" by never acting achieves nothing. The resolution: make undo cheap, then act on the
clear cases.

- A **one-command restore** (a tiny `restore.sh` created at backup time) makes reverting trivial.
- **Granular recovery**: because the backup is a full copy, you can pull back a single file without
  undoing everything else. So an over-aggressive pass costs one `cp`, not a full redo.
- With cheap undo in place, "when in doubt, keep" applies to the *genuinely* ambiguous, while clearly
  dead/clearly correct cases are handled decisively. Don't let caution collapse into doing nothing.

## A restore helper (pattern)

At backup time, also write a small restore script so reverting is one command and foolproof:

```bash
#!/usr/bin/env bash
BAK="<path>/<target>.bak-<date>"
TGT="<path>/<target>"
[ -d "$BAK" ] || { echo "no backup; aborting"; exit 1; }
rm -rf "$TGT" && cp -r "$BAK" "$TGT" && echo "restored"
```

## Self-modification caution

When an agent edits its *own* memory or config, it's the best-informed judge **and** the one most able
to quietly drift. Keep the rails on: back up, stay in scope, protect assets, report + restore. The
agent's confidence is not the safety mechanism — the backup is.

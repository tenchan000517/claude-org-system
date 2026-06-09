# Getting started

The minimal adoption path. **Do not install the whole system at once.** Stand up the map, then add
pieces only when a real pain appears.

## Before you start: the safety discipline (always on)

1. Back up before replacing or moving anything (`cp -r target target.bak-<date>`).
2. Touch only the scope of the current step. Nothing else.
3. Add and move; don't delete. Never gut working-rule memory or existing tooling.
4. When in doubt, leave it.
5. After each step, report **what changed** and **the one-line way to undo it**.

## Step 1 — the map (fixed first move; always do this one)

This is the only non-optional step, and it is purely additive (no memory touched yet).

1. Survey what's actually live in your catch-all workspace.
2. Create an `INDEX` at the workspace root: a table of *project / location / status / next action*.
3. Add a leader role note (a `CLAUDE.md`-style file) at the root: "this is the leader; hold the map,
   dispatch to workers, don't hoard project work."

Effect: "where is what?" becomes a one-glance lookup. Undo: delete the two new files.

## Step 2 — start operating in per-project directories (free; the real switch)

From now on, **open your agent in the project's own folder** to do that project's work. Use the
leader/INDEX only as the dispatcher. New memory now accumulates in the right home automatically.
This costs nothing and is the single most effective habit.

## Step 3+ — add one piece, only when a specific pain bites

Pick the piece that matches the pain you actually feel. One at a time.

| Pain you feel | Piece to add |
|---|---|
| "I keep hunting for settings / paths / accounts" | Stand up the **secretary** (`secretary/KB.md`) |
| "One project's notes are drowning the others" | Move that project's memory into its worker dir (back up first) |
| "My working rules are scattered everywhere" | Promote universal rules to the runtime's **global** config |

For the secretary: start as an **index** (pointers + key points; originals stay), then progressively
**move** the infra/reference notes into the secretary's home (back up; move, don't delete) so the
catch-all actually slims down. "Protect reference" means *don't delete it* — not *don't relocate it
to its proper home.*

## Anti-stall

A purely "add only when in pain" rule can stall into never adopting anything. That's why **Step 1 is
fixed**: always build the map first. After that, let lived friction drive the rest.

## The optional layer (decide separately)

Companion tooling (mascots, helper agents, extra automation) is **not part of the core**. The core
(leader / secretary / workers) must work without it. Adopt optional tools later, on their own merits,
watching for conflicts with what you already run.

# Memory model

The heart of the system. Get routing right and the pile never forms.

## Per-directory scoping is the enabler

Agent runtimes typically keep separate memory per working directory. So *where you open the agent*
determines *which memory loads*. Doing each project's work in its own directory splits memory
automatically — no manual sorting needed for new work.

## Routing rule — where each kind of knowledge lives

| Kind of knowledge | Home |
|---|---|
| Project-specific state, decisions, working notes | that **worker** directory's memory |
| Infrastructure / lookup facts (paths, accounts, configs, standing references) | the **secretary** |
| Roster, cross-project decisions | the **leader** |
| Universal working rules ("always verify facts with tools", house style) | the runtime's **global** config |

The single most important line: **project knowledge never settles in the leader.** You may *act* at
the leader; the knowledge you gain routes to the worker.

## Memory types (and how cleanup treats them)

- **Working-rule / feedback** — accumulated "how we work." A *function*, not noise. Never deleted by
  cleanup. If it's universal, promote it to global config so every directory inherits it.
- **Reference** — facts you look up. Belongs in the **secretary**. Cleanup never deletes it; migrating
  it to the secretary is relocation to its proper home, not deletion.
- **Project** — state of ongoing work. Lives in its worker. *This* is what cleanup prunes when a
  project is migrated, finished, or superseded.
- **User / org facts** — durable facts about who/what. Keep; rarely changes.

## Cleanup (denoise) — safely shrinking a pile

When a catch-all memory must be slimmed:

1. Back up the whole memory directory first.
2. Auto-keep working-rule and reference types (protected). Only **project**-type entries are candidates.
3. A project entry is a removal candidate only if it is **clearly dead**: migrated elsewhere (its real
   home is another directory), finished/resolved with no reuse value, a completed-task log, or an exact
   duplicate. Otherwise it lives.
4. When unsure, keep.
5. Deletions are reversible (the backup); recover a single file by copying it back — no need to
   restore everything.

## Why this matters beyond tidiness

A bloated, mixed memory doesn't just slow sessions — it becomes *raw material for confusion*: an agent
can mistake stale standing-task notes for live instructions. Lean, routed memory removes that fuel.

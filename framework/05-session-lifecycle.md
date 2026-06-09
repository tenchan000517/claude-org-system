# Session lifecycle

How a single working session opens, runs, and closes so that the next session inherits a clean state.

## On startup — get oriented, don't re-derive

- In the **leader**: read the leader role note and the `INDEX` (and any `HANDOFF`). You now know what's
  live and where.
- In a **worker**: read that worker's role note, its `HANDOFF` (current target/state/blocker), and its
  own memory. You're scoped to this one project.
- For any infrastructure/lookup question: consult the **secretary** rather than reconstructing facts.

## During the session — route as you go

- Do the work in the right directory.
- New project knowledge → settles in the worker's memory. Infra facts learned → go to the secretary.
- Apply the safety rules to any structural change (back up, scope, additive, report+restore).

## On close — leave it better-oriented than you found it

1. Append a short, time-stamped line to a **worklog** (what happened).
2. Update the **HANDOFF**: current target, state, deadline/blocker, next concrete step.
3. Surface new durable facts/decisions for capture (see the **ingest** template) so the secretary/
   memory stay current without bloating mid-session.

## Capturing facts without bloat (ingest)

Rather than editing the knowledge base mid-task, drop new facts/decisions into an **ingest queue**
(a small dated file) and fold them into the secretary/memory deliberately later. This keeps working
sessions focused and the knowledge base curated rather than accreted. (Optional; solo setups can just
edit the KB directly when small.)

## The point

Every session should start oriented in seconds (read map + handoff, ask the desk) and end leaving the
map and handoff accurate. No session should have to excavate a pile to figure out where things stand.

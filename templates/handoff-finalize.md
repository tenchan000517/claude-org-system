<!-- The session close-out ritual. Its value is in COMBINING these updates into ONE verified step,
     not doing them ad hoc — that's what keeps map / memory / handoff mutually consistent.
     Run as a dry-run first, verify, then apply. -->

# Handoff finalize — session close-out

Run at the end of a working session. **Do it as one combined, verified ritual** — not scattered edits.

## Steps (in order)

1. **Worklog** — append a timestamped line: what happened this session.
2. **HANDOFF** — update target / state / deadline-or-blocker / next concrete step.
3. **Memory routing** — confirm new knowledge landed in the right home: worker (project), secretary
   (infra/reference), leader (roster/cross-project), global (universal rules). Nothing project-specific
   left sitting in the leader's catch-all.
4. **Secretary ingest** — drop new durable facts/decisions into the secretary's `ingest/` for folding in.
5. **INDEX** — reflect a one-line status update upstream.

## Dry-run verification (the important part)

Before applying, **show the proposed changes** (the diffs / what each step will write) and check they're
what you intend. Only then apply. If anything overwrites, back it up first (safety rules). This
verification is why finalize is a *ritual*, not a reflex — it catches a wrong handoff before it ships.

## Why combined

Done ad hoc, these drift apart: the HANDOFF says one thing, memory another, the INDEX a third. One
verified close-out keeps them in sync, so the next session inherits a coherent state instead of
excavating inconsistencies. This is the ritual that closes the operating loop (`framework/11-operating-rhythm.md`).

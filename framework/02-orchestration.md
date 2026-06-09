# Orchestration

How work flows through the roles without re-creating the catch-all.

## The INDEX is the single source of truth for "what & where"

The leader's `INDEX` is the map. It lists every live project: name, location (the worker directory),
status, and next action. It also carries cross-project decisions. It does **not** carry any single
project's working detail — that lives in the worker.

Keep it honest: dormant/finished projects move to a "not active" section or out entirely, so the map
shows *what's live now*, not the full history.

## The dispatch loop

1. You open the **leader**. You see the map.
2. You pick a project. The leader points you to its **worker** directory.
3. You open the agent **in that worker directory** and do the work there.
4. When status changes, a **one-line update** flows back to the `INDEX`.
5. Any lookup needed along the way (path, account, setting, term) → ask the **secretary**.

Light or cross-cutting work may happen at the leader, but its *project-specific output is routed to
the worker's memory* (see `03-memory-model.md`).

## Handoff between sessions

A worker (or the leader) that will be picked up later leaves a short **HANDOFF**: current target,
state, deadline/blocker, and the next concrete step. The next session reads the HANDOFF and the
INDEX first, and is immediately oriented — no re-deriving context from a pile.

## Reporting up (optional, larger orgs)

Where an executive/domain-lead layer exists, periodic reports roll status upward in a fixed format
(`templates/reports/monthly-report.md`). Solo setups skip this; the INDEX + HANDOFF already carry
"where things stand."

## What orchestration must never become

- A place that accumulates project memory (that's the catch-all returning).
- A bottleneck that forbids all in-place work (rigid "leader never acts" is impractical solo).

The balance: **route by where knowledge settles, stay flexible about where labor happens.**

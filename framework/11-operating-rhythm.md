# Operating rhythm (how the pieces combine)

The static structure (roles, memory, governance) is the skeleton. These rituals are the heartbeat.
**The value is in the loop, not the parts** — each piece alone leaks; together they keep the map,
memory, and handoff mutually consistent over time.

## The loop

1. **Intake** — new work/messages enter the inbox and are triaged into the `INDEX` (`09-intake.md`).
2. **Dispatch** — the leader routes an `INDEX` item to a worker (`02-orchestration.md`).
3. **Work** — the worker does it in its own directory; knowledge routes to its home (`03-memory-model.md`).
4. **Monitor** — scheduled watchers surface changes/events back into intake/INDEX (`10-monitoring.md`).
5. **Finalize** — at session close, the **handoff-finalize** ritual updates worklog + HANDOFF + memory +
   secretary, **dry-run-verified**, so the next turn inherits a consistent state
   (`templates/handoff-finalize.md`, `05-session-lifecycle.md`).
6. → back to 1.

## Why "combined" is the whole point

Each ritual alone leaks:

- Intake without finalize → accepted work never closes cleanly; state drifts.
- Monitoring without intake → events fire into a side channel and bypass triage.
- Finalize without routing → memory piles in the wrong home (the catch-all returns).
- Work without intake/monitor → the org only does what someone happens to remember.

The rhythm is what makes the structure *live* rather than sit as static folders. A team adopting this
should wire the loop, not just copy the templates.

## Governance sits above the loop

Direction-level decisions (`08-governance.md`) shape **what intake accepts** and **what monitors
watch**. A resolution to drop a line of work means intake declines it and its monitors are retired.
The loop executes; governance steers it.

## Scale note

A solo operator runs a tiny version: the inbox is a short list, monitoring is one or two scheduled
checks, finalize is a 5-line close-out. The *shape* of the loop is identical at any size.

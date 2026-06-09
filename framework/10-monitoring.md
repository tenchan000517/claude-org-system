# Monitoring (watch & react without babysitting)

How the org watches state and reacts on a schedule, so no one has to sit and poll. Monitoring doesn't
act off to the side — it **feeds the same loop**: a fired trigger becomes an intake item or an `INDEX`
update.

## A watchlist

Each watched thing is one row: **what** is watched, **how often**, the **trigger** condition, and the
**action** (which routes back into intake/INDEX). Template: `templates/monitor/watchlist.md`.

## Use the runtime's scheduler — abstractly

Cron, scheduled wake-ups, a monitor primitive, background tasks — use whatever the runtime offers. The
framework is tool-agnostic; the pattern is "watch on a cadence, react into the loop."

## Cadence discipline

- Poll only as often as the thing **actually changes**. Watching a slow thing every minute burns
  cycles for nothing.
- Use a **long fallback heartbeat** for rarely-changing state; reserve short polls for genuinely
  fast-moving external state you can't be notified about.
- If the runtime can *notify* you on change, prefer that over polling.

## React into the loop, not off to the side

A fired trigger creates an **intake item** or an **INDEX update** — the same front door as everything
else. This keeps monitoring from becoming a hidden side channel that bypasses triage and routing.

## Safety

Automated/unattended actions follow the same rules as any change: **reversible, scoped, reported**.
A watcher should not take an irreversible action unattended — it should *surface* the situation into
intake for a deliberate call, unless the action is explicitly safe and reversible.

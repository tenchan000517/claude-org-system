<!-- What the org watches automatically, and what each watcher does when it fires.
     Actions route back into the inbox / INDEX — not off to the side. -->

# Watchlist

| What is watched | How often | Trigger condition | Action (→ inbox / INDEX) | Notes |
|---|---|---|---|---|
| <external state / job / queue> | <cadence> | <when X becomes true> | <create intake item / update INDEX> | <reversible? notify vs poll?> |
| <a long-running task> | <on completion> | <task finished/failed> | <surface result into inbox> | … |

## Rules
- Poll only as often as the thing actually changes; prefer notify-on-change over polling.
- A fired trigger **surfaces into intake** for a deliberate call — it does not take irreversible
  action unattended.
- Retire a watcher when a resolution drops the work it was watching.

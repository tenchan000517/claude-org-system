# Operations (running it on a real machine)

The framework is tool-agnostic; this page names the practical concerns of *running* it on one machine,
with common tools as examples. A solo operator needs only a little of this — don't build an ops
platform for an audience of one (`PHILOSOPHY.md` #9).

## Session management & persistence

The model has you open agents in multiple directories (workers) and run monitors in the background. On
one machine you need a way to run **multiple concurrent sessions and keep them alive** across
disconnects.

- The canonical tool is a terminal multiplexer (**tmux**, or `screen`): one persistent session per
  worker/monitor, detach and reattach without losing state.
- Some agent runtimes have a native concurrency / teammate / background mode — prefer it if it fits.
- Pattern: one named session per role, started in that role's directory. Example:
  `tmux new-session -d -s worker-x -c /path/to/worker-x 'claude'`
- Tool-agnostic in principle: the requirement is "concurrent + persistent sessions," not tmux itself.

## Background processes (monitors, daemons)

Monitoring (`10-monitoring.md`) and scheduled work run as background processes. Keep them **supervised
and restartable** so a disconnect or crash doesn't silently kill your watchers.

- A long-running watcher belongs in its own persistent session (tmux) or a supervised service
  (e.g. systemd / launchd) — not a foreground shell you'll close.
- A daemon that spawns agent sessions (e.g. a periodic check that opens a session) should log and
  self-recover.

## Logging

Capture what happened at two levels:

- **Human level** — the worklog / HANDOFF (`05-session-lifecycle.md`): "what this session did."
- **Machine level** — process/session output to log files, so a background failure is diagnosable
  after the fact. A monitor that fails silently is worse than no monitor.

## Notifications

Events that need a human get surfaced, not buried. A fired monitor, a blocked task, or a finished
long job notifies you — and lands in the inbox (`09-intake.md`). Use whatever the runtime/OS offers
(push, desktop notification, a message channel). The principle: don't make the human poll — let the
system raise its hand.

## Scale note

Solo: a couple of tmux sessions + one or two background checks + the worklog *is* your entire ops
layer. Larger: supervised services, centralized logs, a real notification channel. Take only what the
number of moving parts actually requires.

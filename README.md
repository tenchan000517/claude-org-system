# claude-org-system

*English: this page ／ 日本語: [`ja/README.md`](ja/README.md)*

A minimal, reusable **organizational operating system for AI coding agents** (Claude Code and similar).
It turns a single overloaded workspace into a clean **leader → secretary → workers** structure, so context
stays scoped, "where is what?" is always answerable, and the system never silently breaks.

> This is an original methodology. It is published **for reference**. See [LICENSE](LICENSE)
> (CC BY-NC-ND 4.0): you may read and learn from it with attribution; commercial use and
> redistribution of modified versions are not permitted.

---

## The problem it solves

When one workspace (one folder) does *everything* — orchestration **and** the actual work for many
unrelated projects — three things rot:

1. **Memory becomes a pile.** Every project's notes accumulate in one place. You can't find anything.
2. **No router.** There's no map of "what exists / where it lives / what state it's in."
3. **Drift & confusion.** A bloated, mixed context makes the agent slower and more likely to act on
   the wrong thing.

## The shape of the fix

Three roles, mapped onto how AI coding agents already work (context scoped per directory):

| Role | What it is | Job |
|---|---|---|
| **Leader** | The orchestration folder | Holds the map, dispatches to workers, does not hoard project work |
| **Secretary** | One inquiry desk (a KB) | Answers "where is X / what's the setting / what's the status" |
| **Workers** | Each project's own folder | Does the real work; keeps only its own project's memory |

The enabling mechanism: **most agent runtimes scope their instructions and memory by working directory.**
So simply *doing each project's work in its own directory* splits the pile automatically.

## What's here

- [`CREDO.md`](CREDO.md) — the foundational document; layers, roles, conduct principles, cadence (everything derives from this)
- [`PHILOSOPHY.md`](PHILOSOPHY.md) — the principles the whole system rests on
- [`GETTING-STARTED.md`](GETTING-STARTED.md) — the minimal adoption path (start here)
- [`framework/`](framework/) — the full model:
  - `01-roles` · `02-orchestration` · `03-memory-model` · `04-safety` · `05-session-lifecycle` (the **core**)
  - `06-judgment` · `07-departments` · `08-governance` (the **org layers**, for multi-domain setups)
  - `09-intake` · `10-monitoring` · `11-operating-rhythm` (the **operating rituals** that make the loop run)
  - `12-operations` (the **runtime layer** — running it on a real machine: tmux/sessions, background processes, logging, notifications)
- [`templates/`](templates/) — fill-in skeletons for every artifact: leader / worker / department CLAUDE.md,
  INDEX, HANDOFF, secretary KB (single-file + structured + RAG + ingest), inbox (intake & triage),
  monitor (watchlist), handoff-finalize (verified session close-out), governance (resolution log,
  strategy review), reports
- [`examples/`](examples/) — worked, fictional examples: [`demo-org/`](examples/demo-org/) (solo) and
  [`multi-department/`](examples/multi-department/) (org scale)

### Core vs complete

The **core** (roles 01–05 + the basic templates) is all a solo operator or single team needs, and works
on its own. The **org layers** (06–08: judgment framework, departments, governance) and the heavier
templates (department credo, resolution log, monthly report) are for multi-domain organizations. Take
only what earns its place — the core never depends on the org layers.

## How to adopt (one sentence)

Stand up the **map** first (an `INDEX` + a leader role note), then add pieces **only when a real pain
appears** — never bolt on the whole apparatus at once. Details in [`GETTING-STARTED.md`](GETTING-STARTED.md).

## Scale honestly

A solo operator needs the leader + a light secretary + per-project folders. A large org may want the
heavier layers (monthly reporting, ingest pipeline, formal KB). **Take only what earns its place.** The
heavy templates here are optional — the core works without them.

# Demo: a multi-department organization

A worked, **fictional** example of the full system at org scale. Everything here is invented —
substitute your own. (For the one-person version, see `../demo-org/`.)

## The situation

"Northwind" is a small studio with several distinct domains. Before, everything lived in one workspace
and one mixed memory; nobody could say cleanly "who owns what" or "are we hitting our numbers."

## The structure (full system wired up)

```
~/northwind/                    <- ORG LEADER (open here to orient & coordinate across departments)
  CREDO.md                      central credo — every department derives from this
  INDEX.md                      org map: departments, leads, domains, status
  secretary/                    SHARED INFRA & INFO desk (all departments ask here)
    KB.md  kb-yaml/  rag-*.md  ingest/
  governance/
    resolution-log.md           settled direction-level decisions
    strategy-2026-01.md         a strategy review's notes
  reports/
    content-2026-01.md          a department's monthly report

~/northwind-content/            <- DEPARTMENT (profit/impact center)
  CLAUDE.md                     department working doc (role, KGI/KPI, scope) — derived from CREDO
  HANDOFF.md
  <worker dirs per project…>

~/northwind-platform/           <- DEPARTMENT (cost/enabling center)
  CLAUDE.md                     ("we don't move the headline number; we enable those who do")
  HANDOFF.md

~/northwind-clients/            <- DEPARTMENT (profit/impact center)
  CLAUDE.md
  HANDOFF.md
```

## How it holds together

- **CREDO** is the trunk. Each department's `CLAUDE.md` states *its* role, center-type, and targets, and
  **inherits** the conduct principles instead of restating them.
- The **org INDEX** lists departments + leads + status — the leader's map, one level up.
- The **secretary** is shared: every department asks it for paths, accounts, settings, glossary —
  nobody re-derives infrastructure.
- **Governance**: direction decisions are logged as resolutions and bind departments until re-decided;
  a periodic strategy review produces them.
- **Accountability**: each profit/impact department owns a KGI; the enabling department is judged by
  what it enables, not a headline number it can't move. Leads report up monthly in a fixed format.

## How it was adopted

Same incremental path as the solo demo, one level up: stand up the **org map + CREDO** first; give each
department its own directory + working doc; share the **secretary**; add **governance** (resolution log)
when more than one accountable party needed to coordinate; add **reporting** when comparability over
time started to matter. Nothing heavy was added before it earned its place.

## Scale-down note

A solo operator collapses this: the executive, leads, and leader are all you; departments become
project folders; governance is a decision list in the secretary. The *shape* is identical — only the
number of people changes. See `../demo-org/`.

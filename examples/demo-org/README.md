# Demo: a solo operator with several projects

A worked, **fictional** example showing the whole system wired up. Names and details are invented —
substitute your own.

## The situation (before)

"Sam" is a one-person studio doing: a client video edit, a marketing-site build, a recurring monthly
report, and ad-hoc admin. Everything was done in one `~/work` folder. Its memory had ~40 mixed notes;
finding "which mail server does client X use?" meant scrolling. Sessions felt slow and Sam sometimes
acted on stale notes.

## After: the structure

```
~/work/                      <- LEADER (open here to get oriented & dispatch)
  CLAUDE.md                  (leader role note)
  INDEX.md                   (the map: 4 projects, status, next action)
  secretary/                 <- SECRETARY (the inquiry desk)
    KB.md                    (mail settings, asset paths, account notes, glossary)
    rag-video-pipeline.md    (the repeatable edit procedure + gotchas)
~/work-client-edit/          <- WORKER (open here to do the edit)
  CLAUDE.md                  (worker role note)
  HANDOFF.md
~/work-marketing-site/       <- WORKER
  CLAUDE.md
~/work-monthly-report/       <- WORKER
  CLAUDE.md
```

## How a day goes

1. Sam opens the agent in `~/work` → reads `INDEX.md` → sees the client edit is "in progress, next:
   cut section 3."
2. Sam opens the agent in `~/work-client-edit/` → reads its `HANDOFF.md` → does the cut. New notes
   settle in *this* worker's memory, not the leader's.
3. Mid-edit, "what codec did we standardize on?" → Sam asks the **secretary** (`secretary/KB.md`)
   instead of guessing.
4. Done for the day → updates `HANDOFF.md` (next: audio pass) and a one-line status in the leader's
   `INDEX.md`.

## How it was adopted (incrementally, matching GETTING-STARTED)

- **Step 1:** made `INDEX.md` + leader note. (Map only; nothing else moved.) Pain dropped immediately.
- **Step 2:** started opening each project in its own folder. New memory began landing in the right home.
- **Step 3 (a week later, when "where's that setting?" kept biting):** stood up `secretary/KB.md` as an
  index, then progressively *moved* the reference notes into it (backed up first) so `~/work` slimmed down.
- Skipped: monthly executive report layer (the INDEX already shows status for one person), and any
  companion tooling (kept optional).

## The result

Opening any folder loads only that scope. "Where is what?" is a one-glance lookup. The leader's memory
is just the roster. Nothing was deleted that mattered — reference notes were *relocated* to their home,
and every step had a one-line undo.

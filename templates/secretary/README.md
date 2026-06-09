# The secretary as a KB system

The secretary is the org's **shared infrastructure & information desk**. At its simplest it's one
`KB.md`. As it grows, it becomes a small knowledge base with these parts:

```
secretary/
  KB.md                 single-file form (solo / small) — facts, decisions, references, glossary
  kb-yaml/              structured form (grows past one file)
    facts.yaml          settings, paths, accounts, configuration values
    decisions.yaml      decisions of record + why
    glossary.yaml       names, aliases, what-means-what
  rag-<topic>.md        one page per topic asked about repeatedly (fluency in that topic)
  ingest/               new facts dropped here mid-session, folded in deliberately later
```

## What it owns

- **Infrastructure facts** — the shared "where is X / what's the setting / what account" knowledge that
  every role would otherwise re-derive. This is the **infrastructure sharing** layer: define it once,
  everyone asks here.
- **Decisions of record** — so settled questions aren't relitigated (mirrors the resolution log at the
  work level).
- **Glossary** — one canonical name per thing.
- **RAG pages** — deeper, repeatable topics get a dedicated page with key facts, procedure, and gotchas.

## How roles use it

- Workers and leads **ask** the secretary instead of hoarding infra facts in their own memory.
- Reference/infra knowledge **lives here** — when it's scattered in project memories, migrate it in
  (move, don't delete; back up first). "Protect reference" means don't *delete* it, not don't *relocate*
  it to its home.

## Ingest discipline (avoid mid-task bloat)

Drop new facts/decisions into `ingest/` during a session; fold them into the KB deliberately later.
This keeps working sessions focused and the KB curated rather than accreted. Solo/small setups can edit
the KB directly when the change is small.

## The Q&A stance

Open the secretary to **answer**, not to do project work. It's a desk: it returns facts and pointers.
Project work happens in the worker directories.

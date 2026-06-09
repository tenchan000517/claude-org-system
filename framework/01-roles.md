# Roles

Four roles. A solo setup uses the middle two heavily and can fold the top one in. A larger org gives
each its own person/session.

## Leader (orchestration)

The workspace you open to get oriented and to dispatch. It is **not** where project work piles up.

- Holds the **map** (the `INDEX`): what projects exist, where they live, their status.
- Routes a request to the right worker, or starts cross-cutting/light work itself.
- Its memory holds only **roster + cross-project decisions** — never a given project's details.

Flexibility note: the leader *may* do quick or cross-cutting work in place. The discipline is that any
**project-specific knowledge it produces is routed to that worker's memory**, not kept at the leader.

## Secretary (the inquiry desk)

One place to answer "where is X / what's the setting / what's the status / what does this term mean."

- Holds **infrastructure & lookup facts**: paths, accounts, configuration values, standing references,
  decisions-of-record, glossary.
- Is consulted, not worked-in. Workers and the leader ask it; they don't each re-derive the facts.
- It is the **proper home for reference/infra knowledge** — such knowledge should live here, not
  scattered across project memories.

## Workers (the doers)

Each project/domain has its own directory. This is where the actual work happens.

- Does the real work for its one project.
- Keeps **only its own project's memory** — never other projects'.
- When its status changes, reflects a one-line update up to the leader's `INDEX`.
- For lookups (paths, settings, terms), asks the secretary rather than hoarding infra facts.

## Executive / domain-lead (optional, for larger orgs)

Above several workers in one domain, a lead can own outcomes, set priorities, and report up
(see `templates/reports/monthly-report.md`). **A solo operator usually folds this into the leader.**
Only introduce it when there are genuinely multiple domains needing separate accountability.

## The one mechanism that makes this cheap

Because agent runtimes scope instructions and memory **per directory**, these roles are mostly
*placement*: a role note (`CLAUDE.md`) and the right memory living in the right folder. Opening the
agent in a given folder *is* stepping into that role.

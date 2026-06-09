# Philosophy

The principles the whole system rests on. Everything else (roles, templates, procedures) is just
these principles made concrete.

## 1. Separate orchestration from work

One place that *knows what exists and routes* (the leader) must not also *hoard the doing* (the work).
When they merge, the workspace becomes a catch-all and its memory becomes an unsearchable pile.
Keep the map and the labor in different rooms.

## 2. Scope context by location

Modern AI coding agents load their instructions and memory **per working directory**. This is the
cheapest lever you have: do each project's work in its own directory and the context splits itself.
Most of this system is just *placing things where the runtime will scope them correctly.*

## 3. Route by where knowledge lives, not where work happens

You may do a quick or cross-cutting task anywhere. The rule that actually prevents pile-up is about
**memory, not labor**:

- project-specific knowledge → the **worker** directory's memory
- infrastructure / lookup facts → the **secretary**
- roster and cross-project decisions → the **leader**
- universal working rules → the runtime's **global** config

Flexibility in *where you act* is fine, as long as *where knowledge settles* is disciplined.

## 4. Safety comes from reversibility, not from inaction

It is tempting to make a system "safe" by making it never act ("when in doubt, do nothing"). That
trades the goal away — nothing improves. Real safety is: **back up first, change additively, keep a
one-command undo.** Because mistakes are cheap to reverse, judgment can be *decisive* on the clear
cases. Reversibility buys you the right to act.

## 5. Verify; don't assume

Do not assert that a thing exists / is true / was done because it seems so. Check the actual file,
the actual state, the actual source — then state it. This applies to your own prior reports too: a
report is a claim, not a verification.

## 6. Minimal interpretation; no goodwill additions

Do the thing asked, at its smallest faithful size. Don't widen scope, don't "improve" by adding what
wasn't requested, don't pre-build for imagined future needs. Expansions are a separate, explicit
decision — not a default.

## 7. Cost discipline

Context bloat is a tax on every future turn (slower, costlier, more error-prone). A lean, scoped
workspace is not just tidy — it is *cheaper and more reliable*. Trim what is dead; don't carry the
whole history into every session.

## 8. Protect the assets

Working rules (the accumulated "how we work" feedback) and existing tooling are **functions, not
noise**. Cleanup removes dead weight; it must never gut the things that actively steer good behavior.
"Remove noise" and "preserve signal" are the same operation done carefully — not opposites.

## 9. Scale honestly

Take only the parts that earn their place. A solo operator needs little; a large org may need the
heavier layers. Don't transplant a big-org apparatus onto a one-person setup, and don't pretend a
sticky-note covers an enterprise. Right-size, and say out loud what you left out.

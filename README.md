# edukai

**Education for AI models.** A folders-and-files system that gives any LLM agent structured, verified, revisable understanding that survives sessions — memory done as pedagogy instead of storage.

No runtime, no database, no lock-in. Just conventions any agent can follow with `cat` and an editor.

## Why education, not memory

Memory systems store *events*: what happened, when. Education builds *understanding*: what is true, how sure we are, where it came from, and whether it still holds.

1. **Lessons, not logs.** Atomic, titled claims with evidence and caveats — not diary fragments.
2. **Verification over trust.** Every lesson carries a confidence level (`tested` / `observed` / `inferred`) and a `verified` date. Stale lessons get re-checked before high-stakes use.
3. **Distillation pipeline.** Raw capture becomes atomic lessons; lessons are synthesized into domain overviews.
4. **Supersede, never delete.** Changed facts mark old lessons superseded; history is knowledge, and git tracks the diffs.
5. **Economize context.** Layered loading (index → overview → lessons) beats always-on injection at lower token cost; hot-path files stay byte-stable.

## How to use it

Two store types, used together, never merged:

- **Project store** (`<repo>/edukai/`) — knowledge about that codebase, committed inside the host repo.
- **Global store** — one instance, a private GitHub repo of your own: you — preferences, people, cross-project tooling.

**Split rule:** codebase-specific → project store; personal or spanning projects → global store; uncertain → global.

Three steps at a glance (full runbook: [`ADOPT.md`](ADOPT.md)):

1. Copy the skeleton: `cp -r skeleton/ <repo>/edukai`
2. Wire discovery into the host repo's `AGENTS.md` — snippet supplied in `ADOPT.md`.
3. Seed one real domain following `edukai/templates/domain.md`. An empty domain is a bug.

Then point your agent at the store. It reads `edukai/SYLLABUS.md` first, then a domain's `overview.md`, then lessons on demand, and follows `edukai/AGENTS.md` for everything else — read/write protocols, token and cache budgets, verification cadence. Nothing else is required of you.

[`example/`](example/) shows every file shape on a fictional corpus — start there if you learn by reading.

## Your store is private by design

An education store earns its keep by holding the truth unfiltered: preferences, mistakes, operational facts, people. It will accumulate personal knowledge, so keep every store **private**. This kit publishes only the system; your curriculum is yours.

## Updating

Spec copies may drift from this kit on purpose — syncing costs more than divergence, and lessons age by supersession rather than sync. When the kit ships a change you want, re-copy `skeleton/` and resolve differences by hand.

## Licence

MIT — see [`LICENSE.md`](LICENSE.md).

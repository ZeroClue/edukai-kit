# Adopting edukai into another repo

Project stores hold codebase-specific knowledge inside the host repo. This runbook takes about five minutes.

If you also run a global store (a private repo holding preferences, people, cross-project knowledge), adopt it the same way: copy `skeleton/` to its own repo root, delete `skeleton/` itself, and seed one domain.

## 1. Scaffold

```bash
cp -r skeleton/ <repo>/edukai
```

That is a complete store: spec, templates, syllabus, notebook, archives.

## 2. Wire discovery

Add to the host repo's own `AGENTS.md` (create it if missing):

```
This project keeps an education store at ./edukai/.
Session start: read edukai/SYLLABUS.md and follow edukai/AGENTS.md scoped to that directory.
```

## 3. Seed the first domain (same session)

Follow `edukai/templates/domain.md`: name it lowercase-hyphen (`codebase-<project>`), create its folder and overview, register one Syllabus row, write at least one real lesson. An empty domain is a bug.

## Rules that travel with you

- **Split rule**: codebase-specific → project store; personal or spanning projects → your global store; uncertain → global.
- **Git**: heartbeats stage only `edukai/` paths — never sweep unrelated host work. Push belongs to the host repo's normal workflow; project stores do not push autonomously.
- **Durability**: host stores inherit the host repo's push habits. If the repo pushes rarely, prefer a standalone clone instead.
- **Deliberate adoption**: a store needs a standing concern. Do not scaffold one for a one-off visit.

When you run a global store alongside, register the adoption in its `ADOPTED.md` ledger.

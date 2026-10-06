---
title: CI runs tests via `btest`, not make
domain: example
created: 2026-08-23
verified: 2026-08-23
confidence: tested
status: active
supersedes: lessons/2026-08-20-tests-run-via-make.md
superseded_by:
tags: [testing, build, ci]
---

As of 2026-08-22 the project runs its suite through `btest`, a small wrapper that shards unit and integration tests across containers. `make test` still exists but now shells out to `btest` and is deprecated.

## Evidence

- Decision with the author, 2026-08-23.
- `.github/workflows/ci.yml` invokes `btest run --shard auto`.

## Caveats

- Local runs still work via the old make target, so muscle memory gives false confidence.

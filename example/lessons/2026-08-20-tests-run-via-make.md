---
title: Tests run via `make test`
domain: example
created: 2026-08-20
verified: 2026-08-20
confidence: tested
status: superseded
supersedes:
superseded_by: lessons/2026-08-23-ci-switched-to-btest.md
tags: [testing, build]
---

Running `make test` in the project root compiles the test binary and executes the full unit suite. Exit code 0 means green.

## Evidence

- Ran `make test` locally on 2026-08-20; passed in ~40s.

## Caveats

- Requires `docker compose up -d db` first or the integration half fails.

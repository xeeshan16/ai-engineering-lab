# AI Engineering Lab

Production-grade applied AI systems, built one project per week.

Each project tackles one hard problem that engineering teams running LLMs in production hit
this month, and is built the way it would be at work: strong typing, a provider interface with a
deterministic fake (so tests, CI and demos need no paid API keys), an evaluation harness with
measured results, OpenTelemetry tracing, cost accounting, written-down security considerations,
ADRs, and its own CI pipeline.

## Projects

| # | Project | What it does | Status | Stack |
|---|---------|--------------|--------|-------|
| 01 | [Agent Replay](https://github.com/xeeshan16/agent-replay) | Record, replay and regression-gate AI agent trajectories: deterministic tool replay, first-divergence diffing, layered scoring and a CI gate | ✅ Completed | Python 3.12, pydantic, OpenTelemetry, PostgreSQL, FastAPI |
| 02 | [Kafka LLM Enricher](https://github.com/xeeshan16/kafka-llm-enricher) | Exactly-once, budgeted LLM enrichment of Kafka streams: a Postgres result ledger so replays never re-pay, schema-validated output, per-key ordering, rate limits, token budgets and dead-letter topics | ✅ Completed | Java 21, Spring Boot 3, Spring Kafka, PostgreSQL, Micrometer, OpenTelemetry |

## Conventions

- From project 02 onward every project lives in its own repository (linked above) with its own CI.
  Language is chosen per project (Java, Go or Python).
- `projects/<NN>-<slug>/` is a self-contained project with its own `pyproject.toml`, tests,
  evals, docs, Dockerfile and README. Projects that grow into their own repository are linked
  from the table above instead.
- `.github/workflows/<NN>-<slug>.yml` runs lint, type-check, tests and the eval smoke test for
  that project only (path-filtered).
- [`registry.json`](registry.json) records each project's status and dates.
- Results tables only contain numbers that were measured, together with the provider that
  produced them.

## License

[MIT](LICENSE)

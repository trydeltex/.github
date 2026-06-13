<h1 align="center">Deltex</h1>

<p align="center">
  <b>SQL that runs at the edge.</b><br>
  A PostgreSQL-flavored query engine compiled to WebAssembly and deployed across a global edge network.<br>
  No origin server. No cold starts. Queries execute at the node closest to your user.
</p>

<p align="center">
  <a href="https://deltex.dev">Website</a> ·
  <a href="https://deltex.dev/docs">Docs</a> ·
  <a href="https://dash.deltex.dev">Console</a> ·
  <a href="https://deltex.dev/pricing">Pricing</a>
</p>

---

## Official SDKs

| Language | Package | Repo |
|----------|---------|------|
| TypeScript / JavaScript | `@deltex/client` | [deltex-js](https://github.com/trydeltex/deltex-js) |
| Python | `deltex` | [deltex-python](https://github.com/trydeltex/deltex-python) |
| Go | `github.com/trydeltex/deltex-go` | [deltex-go](https://github.com/trydeltex/deltex-go) |
| Rust | `deltex` | [deltex-rust](https://github.com/trydeltex/deltex-rust) |

## Quick start

```bash
# 1. Get a login code, then exchange it for an API key
curl -X POST https://ctrl.deltex.dev/v1/magic-key \
  -H 'Content-Type: application/json' -d '{"email":"you@example.com"}'

# 2. Run your first query
curl -X POST https://api.deltex.dev/v1/query \
  -H 'Authorization: Bearer dtx_k_your_key' \
  -H 'Content-Type: application/json' \
  -d '{"sql":"SELECT 1 + 1 AS answer"}'
```

See the [example apps](https://github.com/trydeltex/examples) for analytics, vector search, GraphQL, and a full SaaS todo backend.

## What is Deltex?

Deltex is an edge-native SQL database. The engine itself is compiled to WebAssembly and runs inside the CDN at every point of presence — so there's no database server to provision, no connection pool to manage, and no cold start. You talk to it over plain HTTPS from any language or runtime, including serverless and edge functions.

- **Full SQL** — SELECT, joins, aggregates, window functions, CTEs, JSON, DDL, transactions
- **Edge-native** — low-latency reads from the nearest edge location
- **Just HTTPS** — works in Node, Bun, Deno, Workers, Vercel Edge, and any backend
- **Postgres-compatible** — bring your existing SQL and ORMs (Drizzle, and more)

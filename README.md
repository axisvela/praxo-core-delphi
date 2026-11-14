# PRAXO-CORE for Delphi / Free Pascal

Native Core implementation with source tag `delphi/v0.5.0`. It passes all eleven vector groups and includes the native agent loop plus memory, event, checkpoint, policy, context, and middleware helpers. It does not call Go or another language Core; it includes native OpenAI-compatible, Anthropic, and Gemini model adapters but no process bridge or plugin host.

## At a glance

| Field | Value |
| --- | --- |
| Package | `PRAXO-CORE` |
| Registry | [OPM / GitHub release](https://github.com/axisvela/praxo-core/releases/tag/delphi%2Fv0.2.1) |
| Install | `OPM package or release archive` |
| Source version | `0.5.0` |
| Published version | `0.2.1` |
| Source tag | `delphi/v0.5.0` |
| Tier | Core |
| Contract | `SPEC_VERSION` `0.2.0` |
| Documentation | https://axisvela.github.io/praxo-core/languages/delphi/ |
| License | MIT |

## Highlights

- OpenAI-compatible model: native
- Anthropic model: native
- Gemini model: native
- MCP client: native
- Harmovela sink: native
- OpenTelemetry sink: native (transport seam)
- Subagent delegation: native (synchronous seam)
- Retriever: native

## Quick start

Install the published package:

```text
OPM package or release archive
```

See the [full Delphi / Free Pascal README](language/delphi/README.md) for complete installation, build, and verification commands.

## What's included

| Capability | Status | Detail |
| --- | --- | --- |
| OpenAI-compatible model | native | `TPraxoOpenAIAdapter` with FPC HTTP transport |
| Anthropic model | native | `TPraxoAnthropicAdapter`; FPC HTTP transport |
| Gemini model | native | `TPraxoGeminiAdapter`; FPC HTTP transport |
| MCP client | native | `TPraxoMcpClient`; stdio and `TPraxoHttpMcpTransport` for Streamable HTTP 2025-03-26 |
| Harmovela sink | native | `TPraxoHarmovelaSink` |
| OpenTelemetry sink | native (transport seam) | `TPraxoOtelSink`; caller supplies `TPraxoOtelTransport` |
| Subagent delegation | native (synchronous seam) | `TPraxoSubagentManager.Run`; no asynchronous manager |
| Retriever | native | `TPraxoDocument`, `TPraxoRetriever`, `PraxoRetrieveDocuments` |

## Examples

Runnable examples live under [`language/delphi/examples`](language/delphi/examples).

| Example | What it shows |
| --- | --- |
| [checkpoint](language/delphi/examples/checkpoint) | This example uses the Delphi Core checkpoint allowlist for a registered payload round trip. |
| [event-sink](language/delphi/examples/event-sink) | This example uses Delphi Core sink composition to fan out events and filter the tool-only stream. |
| [identity-policy](language/delphi/examples/identity-policy) | This example binds a trusted principal to policy decisions and rejects missing, role-mismatched, and tenant-mismatched actions. |
| [mcp](language/delphi/examples/mcp) | This example uses a caller-owned in-process transport with the Delphi MCP client. |
| [provider-fallback](language/delphi/examples/provider-fallback) | This example calls a fallback only after the primary fails and preserves the primary failure when both fail. |
| [retry](language/delphi/examples/retry) | This example retries a transient failure with a bounded attempt count and keeps the exhausted failure state. |
| [service](language/delphi/examples/service) | This example defines a transport-neutral request handler with health, principal, and run cases. |
| [streaming](language/delphi/examples/streaming) | This example accumulates streamed chunks and checks that they reconstruct the final output. |
| [structured-output](language/delphi/examples/structured-output) | This example validates a final JSON answer against a schema and rejects invalid output. |

## Verify

Run the checks from `language/delphi`:

```bash
python language/delphi/run-tests.py
python language/delphi/api-snapshot.py --check
```

This mirror contains the language source and the shared `spec/` vectors, so the implementation can be built and tested here. See [`language/delphi/README.md`](language/delphi/README.md) for the exact commands. The monorepo CI runs conformance, API snapshot, and native tests for this implementation.

## Community

- X: <https://x.com/axisvela>
- Weibo: <https://weibo.com/u/1936025761>

## Repository layout

- `language/delphi/` — implementation source, tests, API snapshot, and examples
- `spec/` — shared contract, vectors, and parity inventories
- `LICENSE` — MIT license

## Canonical source

- Canonical source: https://github.com/axisvela/praxo-core/tree/main/language/delphi
- Registry introduction: `language/delphi/REGISTRY.md`
- Machine-readable entry: `language/delphi/llms.txt` and `language/delphi/llms.md`
- Mirror repository: https://github.com/axisvela/praxo-core-delphi
- Release index: https://axisvela.github.io/praxo-core/languages/registry-status/

This repository is a discovery mirror of the canonical Delphi / Free Pascal source. The monorepo remains the source of truth and the release workflow source.

PRAXO-CORE is not a hosted model, workflow engine, identity provider, or safety controller. Do not infer exactly-once execution, complete sandbox isolation, production security certification, live-provider behavior, or physical safety from this package.

MIT licensed.

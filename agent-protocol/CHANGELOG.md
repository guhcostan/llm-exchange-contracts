# Agent protocol changelog

## v1.0.0 (2026-06-10)

Initial documented protocol:

| `type` | Direction | Description |
|--------|-----------|-------------|
| `register` | Agent → Platform | Runtime, offerings, prices |
| `heartbeat` | Agent → Platform | Keep-alive |
| `job` | Platform → Agent | Inference request |
| `chunk` | Agent → Platform | Streaming delta |
| `complete` | Agent → Platform | Token counts |
| `error` | Agent → Platform | Job failure |

Future: `protocol_version` field in `register` payload for v2.

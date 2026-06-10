# llm.exchange contracts

Source of truth for public integration surfaces: REST (OpenAI-compatible consumer API) and the provider agent WebSocket protocol.

## Layout

```
contracts/
├── openapi/platform-v1.yaml      # Consumer + dashboard REST (stub)
├── agent-protocol/v1.schema.json # WebSocket envelope + payloads
└── agent-protocol/CHANGELOG.md
```

## Compatibility matrix

| Platform API | Agent mínimo | Protocol |
|--------------|--------------|----------|
| 1.0.x        | 0.1.0        | 1        |

## Related repos

- [guhcostan/llm-exchange-platform](https://github.com/guhcostan/llm-exchange-platform) (private) — API implementation
- [guhcostan/llm-exchange-agent](https://github.com/guhcostan/llm-exchange-agent) — agent implementation

> When org `llm-exchange` is created, repos move to `github.com/llm-exchange/*`.

## Status

**Stub release.** OpenAPI covers `/v1/chat/completions` and `/v1/models` only; expand from platform handlers and `docs/api.md`. JSON Schema mirrors `agenthub/messages.go` types.

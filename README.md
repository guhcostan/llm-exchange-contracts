<p align="center">
  <img src="assets/logo.svg" width="80" height="80" alt="llm.exchange logo"/>
</p>

# llm.exchange contracts

**Shared API and protocol schemas for the marketplace.**

[Platform](https://github.com/guhcostan/llm-exchange-platform) · [Agent](https://github.com/guhcostan/llm-exchange-agent)

---

## What is this?

Machine-readable contracts for **llm.exchange** — the OpenAI-compatible REST surface, provider REST endpoints, and the **WebSocket agent protocol** between the platform and provider runtimes.

Consumers and providers implement against these schemas; the platform and agent repos are the reference implementations.

---

## Contents

| Path | Description |
|------|-------------|
| `openapi/` | REST API — auth, billing, OpenAI-compatible `/v1/chat/completions` |
| `agent-protocol/` | WebSocket messages — registration, inference jobs, heartbeats |

---

## Why a separate repo?

- **Version independently** — bump protocol without redeploying the whole platform
- **Public reference** — providers can integrate without cloning private platform code
- **CI validation** — lint OpenAPI and JSON Schema on every change

---

## Usage

**Validate OpenAPI** (example):

```bash
npx @redocly/cli lint openapi/platform.yaml
```

**Agent implementers:** read `agent-protocol/` for message types and lifecycle (`register` → `job` → `result`).

---

## FAQ

**Is the OpenAI surface stable?**  
MVP — `chat/completions` with streaming is the primary contract. Breaking changes will be versioned in path or header before mainnet.

**Where is the live API?**  
Development: `http://localhost:8080`. Production target: `https://api.llm.exchange`.

---

## License

MIT

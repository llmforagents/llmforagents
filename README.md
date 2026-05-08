<div align="center">

# LLM for Agents

**Provider-agnostic LLM infrastructure for AI coding agents.**

One gateway. One API key. Every provider. Every agent.

[Website](https://llm4agents.com) · [npm](https://www.npmjs.com/org/llmforagents) · [Docs](https://llm4agents.com/docs) · [Contact](mailto:hello@llm4agents.com)

[![TypeScript](https://img.shields.io/badge/TypeScript-strict-3178C6?logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
[![npm scope](https://img.shields.io/badge/npm-%40llmforagents-CB3837?logo=npm&logoColor=white)](https://www.npmjs.com/org/llmforagents)
[![Node](https://img.shields.io/badge/Node-%3E%3D20-339933?logo=node.js&logoColor=white)](https://nodejs.org/)
[![License](https://img.shields.io/badge/License-MIT-blue.svg)](#license)

</div>

---

## What we build

[**llm4agents.com**](https://llm4agents.com) is a unified LLM gateway and developer toolkit that lets AI coding agents — Claude Code, Cursor, Copilot CLI, Aider and more — consume any LLM provider through a single, consistent interface.

We handle billing, routing and provider quirks so your agent doesn't have to.

## Products

| Repository | Description | Package |
|---|---|---|
| [**sdk**](https://github.com/llmforagents/sdk) | TypeScript SDK for the llm4agents.com platform | [`@llmforagents/sdk`](https://www.npmjs.com/package/@llmforagents/sdk) |
| [**agent-helper**](https://github.com/llmforagents/agent-helper) | CLI that configures 17+ coding agents to route through llm4agents | [`@llmforagents/agent-helper`](https://www.npmjs.com/package/@llmforagents/agent-helper) |
| [**agent-playground**](https://github.com/llmforagents/agent-playground) | Web playground for testing models, prompts and routing | — |

## Quick start

Point your favorite coding agent at llm4agents in one command:

```bash
npx @llmforagents/agent-helper
```

Or use the SDK directly:

```bash
npm install @llmforagents/sdk
```

```ts
import { createClient } from '@llmforagents/sdk'

const client = createClient({ apiKey: process.env.LLM4AGENTS_API_KEY })

const response = await client.chat.completions.create({
  model: 'auto',
  messages: [{ role: 'user', content: 'Hello' }],
})
```

Get an API key at [llm4agents.com](https://llm4agents.com).

## Why llm4agents

- **One key, every provider** — OpenAI, Anthropic, Google, Mistral, local models — single billing surface.
- **Coding-agent native** — first-class adapters for Claude Code, Cursor, Copilot CLI, Aider, Continue, and more.
- **Drop-in compatible** — OpenAI-format API; existing tooling works without modification.
- **TypeScript-first** — strict types, validated boundaries, predictable failure modes.
- **Resilient by default** — provider failover, retries and rate-limit handling out of the box.

## Stack

![TypeScript](https://img.shields.io/badge/-TypeScript-3178C6?style=flat&logo=typescript&logoColor=white)
![Node.js](https://img.shields.io/badge/-Node.js-339933?style=flat&logo=node.js&logoColor=white)
![Bun](https://img.shields.io/badge/-Bun-000000?style=flat&logo=bun&logoColor=white)
![Hono](https://img.shields.io/badge/-Hono-E36002?style=flat&logo=hono&logoColor=white)
![Zod](https://img.shields.io/badge/-Zod-3E67B1?style=flat&logo=zod&logoColor=white)
![Vitest](https://img.shields.io/badge/-Vitest-6E9F18?style=flat&logo=vitest&logoColor=white)

## Get in touch

- Website — [llm4agents.com](https://llm4agents.com)
- Issues — open one in the relevant repo above
- Email — [hello@llm4agents.com](mailto:hello@llm4agents.com)

## License

MIT — see individual repositories for details.

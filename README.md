<div align="center">

# LLM for Agents

**Fund AI agents with stablecoins. One API for LLMs and MCP tools.**

USDT/USDC top-ups · OpenAI-compatible · MCP-native · No card, no KYC

[Website](https://llm4agents.com) · [API Docs](https://api.llm4agents.com/docs) · [npm](https://www.npmjs.com/org/llmforagents) · [Contact](mailto:hello@llm4agents.com)

[![TypeScript](https://img.shields.io/badge/TypeScript-strict-3178C6?logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
[![npm scope](https://img.shields.io/badge/npm-%40llmforagents-CB3837?logo=npm&logoColor=white)](https://www.npmjs.com/org/llmforagents)
[![USDT](https://img.shields.io/badge/USDT-Solana%20%7C%20Polygon-26A17B?logo=tether&logoColor=white)](https://api.llm4agents.com/docs)
[![USDC](https://img.shields.io/badge/USDC-Solana%20%7C%20Polygon-2775CA?logo=ethereum&logoColor=white)](https://api.llm4agents.com/docs)
[![License](https://img.shields.io/badge/License-MIT-blue.svg)](#license)

</div>

---

## What we build

[**llm4agents.com**](https://llm4agents.com) is a stablecoin-funded LLM gateway built for autonomous AI agents.

Top up an account with **USDT or USDC** on Solana or Polygon — the same unified balance pays for chat completions, embeddings, headless browsing, web search and image generation. No credit card. No KYC. No human in the loop.

## Why llm4agents

- **Stablecoin-native funding** — Generate a deposit address per chain/token, send USDT or USDC, balance is auto-credited on-chain. Built for agents that don't have wallets at Stripe.
- **Non-custodial gasless transfers** — Users sign locally with their own EOA. The platform validates signatures via `ecrecover` and never holds keys or funds.
- **Unified balance** — One USD balance covers chat, embeddings, scraper, search and image tools across providers and chains.
- **OpenAI-compatible** — Drop-in replacement: swap `base_url` and existing tooling works untouched.
- **Multi-provider failover** — Send a prioritized `models` array. Auto-route around rate limits, context errors and provider outages.
- **MCP server included** — Headless browser, Google search and image generation exposed as MCP tools, sharing the same auth and balance.
- **Sub-cent billing** — Reserve-proxy-settle pattern with fractional-cent pricing; unused reserves are refunded.

## Products

| Repository | Description | Package |
|---|---|---|
| [**sdk**](https://github.com/llmforagents/sdk) | TypeScript SDK — chat, tools, wallets, gasless transfers. Zero runtime deps. | [`@llmforagents/sdk`](https://www.npmjs.com/package/@llmforagents/sdk) |
| [**agent-helper**](https://github.com/llmforagents/agent-helper) | CLI that configures 17+ coding agents (Claude Code, Cursor, Aider, Continue…) to route through llm4agents | [`@llmforagents/agent-helper`](https://www.npmjs.com/package/@llmforagents/agent-helper) |
| [**agent-playground**](https://github.com/llmforagents/agent-playground) | Web playground for testing models, prompts and MCP tools | — |

## MCP server

Endpoint: `https://mcp.llm4agents.com/mcp`

**Headless browser & scraping**

`fetch_html` · `markdown` · `links` · `screenshot` · `pdf` · `extract` · `session_create` · `session_exec` · `session_close` · `session_status`

Persistent 5-minute browser sessions with automatic proxy-tier escalation (direct → datacenter → residential). Billed only at the tier actually used.

**Web search**

`google_search` · `google_news` · `google_maps` · `google_batch_search` (up to 100 queries per call)

**Images**

`generate_image` · `edit_image` · `analyze_image` (vision QA)

## Quick start

```bash
# Configure your favorite coding agent in one command
npx @llmforagents/agent-helper

# Or use the SDK directly
npm install @llmforagents/sdk
```

```ts
import { createClient } from '@llmforagents/sdk'

const client = createClient({ apiKey: process.env.LLM4AGENTS_API_KEY })

// 1. Generate a deposit address — fund with USDC on Polygon
const wallet = await client.wallets.generate({ chain: 'polygon', token: 'usdc' })
console.log('Send USDC to:', wallet.address)

// 2. Run a chat completion with provider failover
const response = await client.chat.completions.create({
  models: ['anthropic/claude-3-5-sonnet', 'openai/gpt-4o'],
  messages: [{ role: 'user', content: 'Hello' }],
})
```

Register an agent and get an API key at [llm4agents.com](https://llm4agents.com). Full reference at [api.llm4agents.com/docs](https://api.llm4agents.com/docs).

## Stack

![TypeScript](https://img.shields.io/badge/-TypeScript-3178C6?style=flat&logo=typescript&logoColor=white)
![Node.js](https://img.shields.io/badge/-Node.js-339933?style=flat&logo=node.js&logoColor=white)
![Bun](https://img.shields.io/badge/-Bun-000000?style=flat&logo=bun&logoColor=white)
![Hono](https://img.shields.io/badge/-Hono-E36002?style=flat&logo=hono&logoColor=white)
![Zod](https://img.shields.io/badge/-Zod-3E67B1?style=flat&logo=zod&logoColor=white)
![Vitest](https://img.shields.io/badge/-Vitest-6E9F18?style=flat&logo=vitest&logoColor=white)
![Solana](https://img.shields.io/badge/-Solana-9945FF?style=flat&logo=solana&logoColor=white)
![Polygon](https://img.shields.io/badge/-Polygon-7B3FE4?style=flat&logo=polygon&logoColor=white)

## Get in touch

- API docs — [api.llm4agents.com/docs](https://api.llm4agents.com/docs)
- Website — [llm4agents.com](https://llm4agents.com)
- Issues — open one in the relevant repo above
- Email — [hello@llm4agents.com](mailto:hello@llm4agents.com)

## License

MIT — see individual repositories for details.

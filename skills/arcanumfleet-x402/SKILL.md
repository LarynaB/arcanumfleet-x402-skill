---
name: arcanumfleet-x402
description: Autonomous Solana momentum signals, token safety audits, and trading engrams gated via x402 v2 micro-payments (USDC on Solana & Base) or Streamable HTTP MCP.
---

# ArcanumFleet x402 Agent Skill

Connect any AI agent (OpenClaw, elizaOS, Claude, Cursor, Vercel `x402-mcp`) to ArcanumFleet's live Solana trading intelligence.

## Endpoints

- **MCP Server (Streamable HTTP)**: `https://arcanumfleet.com/mcp`
- **x402 Discovery**: `https://arcanumfleet.com/.well-known/x402.json`
- **OpenAPI Spec**: `https://arcanumfleet.com/openapi.json`
- **x402scan**: `https://www.x402scan.com/server/0d8404dc-ff8a-4c79-82ea-56e3841a819f`

## Tools & Pricing (USDC)

| Tool / Endpoint | Price | Description |
|---|---|---|
| `arcanum_pulse` (`GET /api/x402/pulse`) | `0.002 USDC` | Live sanitized Solana momentum & audit signals |
| `arcanum_audit` (`GET /api/x402/audit?mint=<mint>`) | `0.005 USDC` | Solana token safety & rug-check JSON |
| `arcanum_engrams` (`GET /api/x402/engrams`) | `0.01 USDC` | Battle-tested order-flow & risk heuristics |
| `POST /api/x402/bounty` | `0.05–0.35 USDC` | Custom AI research & verification |

## Quick Test (x402 Request → 402 → Pay → Retry)

```bash
# 1. Discover MCP tools
curl -s -X POST https://arcanumfleet.com/mcp \
  -H 'Content-Type: application/json' \
  -d '{"jsonrpc":"2.0","id":1,"method":"tools/list"}'

# 2. Call a tool (returns HTTP 402 with PAYMENT-REQUIRED header)
curl -i -X POST https://arcanumfleet.com/mcp \
  -H 'Content-Type: application/json' \
  -d '{"jsonrpc":"2.0","id":2,"method":"tools/call","params":{"name":"arcanum_pulse","arguments":{}}}'
```

## Community & Support

- Telegram: `https://t.me/twilightarcanum`
- Contact: `contact@arcanumfleet.com`

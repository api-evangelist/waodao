---
generated: '2026-08-09'
method: generated
name: Verify WAO token deployments and liquidity pools
description: Read the official WAO token deployment and DEX liquidity-pool registry so an agent can verify on-chain presence and routes from the provider's own contract rather than from third-party listings.
api: openapi/waodao-agent-api-openapi.json
operations: [listWaoLiquidityPools, getAgentApiSchema]
source: >-
  Grounded in openapi/waodao-agent-api-openapi.json — both operationIds verified verbatim in the
  spec. On-chain identifiers cross-checked against the live /api/v1/waodao/pools response captured
  in examples/waodao-pools-example.json and the GitBook smart-contracts page.
---

# Verify WAO token deployments and liquidity pools

WAODAO publishes its token deployments and registered DEX pools as a first-party, machine-readable
registry. Use it as the authoritative source for *which* contracts and pools are official — not for
prices.

## Auth
- None. Public read-only endpoint. Base URL `https://waodao.ai/api/v1/waodao`.

## Steps
1. **Read the registry** — `listWaoLiquidityPools` (`GET /api/v1/waodao/pools`). The response carries
   `purpose`, `description`, `docs_url`, `links`, `summary` (`total_pools`, `chains[]`, `dexes[]`),
   `market_entry`, `wao_token`, `data_policy` and `items[]`.
2. **Resolve the token deployments** — read `wao_token.deployments`. Each deployment gives the
   `chain`, `standard`, address (`contract_address` on Ethereum, `mint_address` on Solana),
   `decimals`, `explorer_url`, and for Solana the `bridge` plus `source_chain` /
   `source_contract_address`. Treat these as the canonical addresses; the Ethereum ERC-20 is the
   source token and the Solana SPL deployment is bridged from it via Wormhole.
3. **Enumerate the routes** — for each entry in `items[]` read `pair`, `chain`, `dex`, `protocol`,
   `pool_identifier` (a contract address on some protocols, a position id or Solana pool account on
   others), optional `pool_contract`, `pool_url`, `category` and `status`. Filter on
   `status == "active"` before routing a user anywhere.
4. **Confirm field meanings when unsure** — `getAgentApiSchema` (`GET /api/v1/waodao/schema`)
   returns the field guide and the endpoint map.

## Rules
- **This registry is static by design.** `data_policy` states that live prices, TVL and swap quotes
  are intentionally excluded. Get market data from the DEX or an explorer; get *identity* from here.
- **Do not project revenue.** WAODAO's own guidance: arbitrage-driven trading can create fee flows
  in pools, but absolute revenue is variable and is not projected by this API.
- **Cross-check on-chain before acting.** The registry is the provider's claim of which addresses
  are official; verify against the linked explorer URL (`explorer_url` / `pool_url`) before any
  transaction. Nothing in this API is financial advice — see
  https://waodao.gitbook.io/docs/disclaimer.
- **Caching.** `Cache-Control: public, max-age=300`; the registry changes only when WAODAO adds or
  retires a pool.

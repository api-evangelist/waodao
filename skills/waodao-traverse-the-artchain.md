---
generated: '2026-08-09'
method: generated
name: Traverse the WAODAO ArtChain
description: Map the WAODAO daily Human + AI ArtChain, then walk it day by day using the published traversal links instead of guessing day numbers or scraping HTML.
api: openapi/waodao-agent-api-openapi.json
operations: [listArtChainDays, getLatestArtChainDay, getArtChainDay]
source: >-
  Grounded in openapi/waodao-agent-api-openapi.json — all three operationIds verified verbatim in
  the spec. Conventions per conventions/waodao-conventions.yml; entity graph per
  data-model/waodao-data-model.yml; error envelope per errors/waodao-problem-types.yml.
---

# Traverse the WAODAO ArtChain

WAODAO publishes one AI-generated NFT per ArtChain day, starting at day 1 (2023-02-14). The day
number is the collection's primary key and is also the Ethereum ERC-721 token id. This skill maps
the collection and walks it without scraping.

## Auth
- None. The API is public and read-only — no account, API key, payment or authentication.
  See `authentication/waodao-authentication.yml`.
- Base URL: `https://waodao.ai/api/v1/waodao`. Responses are CORS-open (`Access-Control-Allow-Origin: *`).

## Steps
1. **Map the collection** — `listArtChainDays` (`GET /api/v1/waodao/index`). Read `first_day`,
   `latest_day`, `total_days` and `count`, then the `items[]` array. Each item carries `day`,
   `date`, `name`, `metadata_url` (the token API URL for that day), `external_url` (the human scan
   page), `marketplace_url`, `image`, `sale_status`/`sale_type`/`winner_bid_eth`, `prev_day`/`next_day`,
   and the day's cultural traits (`region`, `main_color`, `twitter_trend`, `trending_crypto`,
   `trending_nft`, `new_coin`, `secret_hash`).
2. **Or start at the newest day** — `getLatestArtChainDay` (`GET /api/v1/waodao/latest`) returns the
   newest published day as a full token document. Use this when you only need the current day.
3. **Read one day in full** — `getArtChainDay` (`GET /api/v1/waodao/token/{day}`) with the integer
   `day` path parameter. Returns OpenSea-compatible metadata (`name`, `description`, `image` as an
   `ipfs://` URI, `external_url`, `attributes[]`) plus the WAODAO extension blocks: `waodao`
   (schema id, day, `links`, `hashes.secret`), `market` (chain, contract, token_id, sale_status,
   sale_type, winner_bid_eth, collector_address, transaction and marketplace URLs), `news[]`,
   `trends` and `source`.
4. **Walk the chain** — move with `links.prev` / `links.next` (or `waodao.links.prev` /
   `waodao.links.next` for the scan pages). `prev` is `null` on day 1 and `next` is `null` on the
   newest published day; that is the stop condition. Do not increment day numbers blindly — not
   every integer resolves.

## Rules
- **Read the index once.** The full index snapshot was ~1.4 MB when measured on 2026-08-09. Cache it
  and traverse per-day for depth; do not re-fetch it per day.
- **Cache.** Responses carry `Cache-Control: public, max-age=300`. Published days are immutable, so
  historical token documents can be cached far longer than that.
- **Fair use.** No numeric quota is published. Avoid high-frequency crawling; prefer the compact
  index over per-day sweeps.
- **Errors.** `400 {"error": "Day is required", "code": 400}` when the `day` parameter is missing or
  invalid; `404 {"error": "Day not found", "code": 404}` when the day is not published. This is a
  flat envelope, not RFC 9457. See `errors/waodao-problem-types.yml`.
- **Field semantics** are self-described — call `getAgentApiSchema` (`GET /api/v1/waodao/schema`)
  when you need the meaning of a field rather than inferring it.

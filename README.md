# WAODAO (waodao)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

WAODAO is a daily Human + AI "ArtChain": since 14 February 2023 one AI-generated NFT has been minted every day from world news signals, digital trends, human input and AI art, producing an on-chain cultural archive that stood at 1,272 published days when the index was read on 2026-08-09. The WAODAO Agent API is a public, read-only JSON API — five GET operations, no account, no API key, no authentication, CORS enabled — for traversing that ArtChain day by day and for discovering the official WAO token deployments (Ethereum ERC-20 and a Wormhole-bridged Solana SPL token) and the registered DEX liquidity pools across Uniswap, Balancer and Meteora. The project publishes an unusually complete machine-readable discovery surface for its size: OpenAPI 3.1 and a 3.0.2 compatibility contract, an APIs.json index at both /apis.json and the /.well-known alias, an RFC 9727 API catalog advertised on every response via a Link header, a Postman collection, and llms.txt on both the site and the GitBook docs.

**APIs.json:** [https://waodao.apievangelist.com/apis.yml](https://waodao.apievangelist.com/apis.yml)

## Tags

- AI Agents
- ArtChain
- Human and AI
- NFT Metadata
- On-chain Culture
- Liquidity Pools
- Web3
- OpenAPI
- Ethereum
- Solana
- Agent Native
- Digital Art

## Timestamps

- **Created:** 2026-07-24
- **Modified:** 2026-08-09

## APIs

### WAODAO Art Chain API

Traverse the daily Human + AI ArtChain.

- **Human URL:** [https://waodao.ai/ai-agents](https://waodao.ai/ai-agents)
- **Base URL:** `https://waodao.ai/api/v1/waodao`

#### Tags

- ArtChain

#### Properties

- [OpenAPI](openapi/waodao-artchain-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/waodao-artchain-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/waodao-artchain-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](https://waodao.ai/postman-collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [L L Ms Txt](https://waodao.ai/llms.txt)
- [Documentation](https://waodao.ai/ai-agents)
- [API Reference](https://waodao.ai/ai-agents#api-reference)
- [Getting Started](https://waodao.ai/ai-agents#api-reference)
- [Authentication](https://waodao.ai/ai-agents#api-access)
- [Rate Limits](https://waodao.ai/ai-agents#api-access)

### WAODAO Liquidity Pools API

Discover official WAO token deployments and registered DEX pools.

- **Human URL:** [https://waodao.ai/ai-agents](https://waodao.ai/ai-agents)
- **Base URL:** `https://waodao.ai/api/v1/waodao`

#### Tags

- Liquidity Pools

#### Properties

- [OpenAPI](openapi/waodao-liquidity-pools-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/waodao-liquidity-pools-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/waodao-liquidity-pools-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](https://waodao.ai/postman-collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [L L Ms Txt](https://waodao.ai/llms.txt)
- [Documentation](https://waodao.ai/ai-agents)
- [API Reference](https://waodao.ai/ai-agents#api-reference)
- [Getting Started](https://waodao.ai/ai-agents#api-reference)
- [Authentication](https://waodao.ai/ai-agents#api-access)
- [Rate Limits](https://waodao.ai/ai-agents#api-access)

### WAODAO Schema API

Read WAODAO-specific field semantics and discovery links.

- **Human URL:** [https://waodao.ai/ai-agents](https://waodao.ai/ai-agents)
- **Base URL:** `https://waodao.ai/api/v1/waodao`

#### Tags

- Schema

#### Properties

- [OpenAPI](openapi/waodao-schema-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/waodao-schema-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/waodao-schema-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](https://waodao.ai/postman-collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [L L Ms Txt](https://waodao.ai/llms.txt)
- [Documentation](https://waodao.ai/ai-agents)
- [API Reference](https://waodao.ai/ai-agents#api-reference)
- [Getting Started](https://waodao.ai/ai-agents#api-reference)
- [Authentication](https://waodao.ai/ai-agents#api-access)
- [Rate Limits](https://waodao.ai/ai-agents#api-access)

### WAODAO Token Metadata API

Read agent-friendly metadata for a published WAODAO day.

- **Human URL:** [https://waodao.ai/ai-agents](https://waodao.ai/ai-agents)
- **Base URL:** `https://waodao.ai/api/v1/waodao`

#### Tags

- Token Metadata

#### Properties

- [OpenAPI](openapi/waodao-token-metadata-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/waodao-token-metadata-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/waodao-token-metadata-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](https://waodao.ai/postman-collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [L L Ms Txt](https://waodao.ai/llms.txt)
- [Documentation](https://waodao.ai/ai-agents)
- [API Reference](https://waodao.ai/ai-agents#api-reference)
- [Getting Started](https://waodao.ai/ai-agents#api-reference)
- [Authentication](https://waodao.ai/ai-agents#api-access)
- [Rate Limits](https://waodao.ai/ai-agents#api-access)

## Common Properties

- [Developer Portal](https://waodao.ai/ai-agents)
- [Documentation](https://waodao.gitbook.io/docs/)
- [Support](https://waodao.ai/ai-agents#api-access)
- [Community](https://discord.gg/hsrkWhvDeS)
- [Telegram](https://t.me/waodao_ai)
- [Twitter](https://twitter.com/waodao_ai)
- [Roadmap](https://waodao.gitbook.io/docs/development/roadmap)
- [Disclaimer](https://waodao.gitbook.io/docs/disclaimer)
- [Postman](postman/waodao-agent-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [A P Is J S O N](https://waodao.ai/apis.json)
- [A P I Catalog](https://waodao.ai/.well-known/api-catalog)
- [Well Known](well-known/waodao-well-known.yml)
- [L L Ms Txt](llms/waodao-llms.txt)
- [Authentication](authentication/waodao-authentication.yml)
- [Conventions](conventions/waodao-conventions.yml)
- [Error Catalog](errors/waodao-problem-types.yml)
- [Lifecycle](lifecycle/waodao-lifecycle.yml)
- [Conformance](conformance/waodao-conformance.yml)
- [Data Model](data-model/waodao-data-model.yml)
- [M C P Server](mcp/waodao-mcp.yml)
- [Agent Skill](skills/_index.yml)
- [Overlay](overlays/waodao-agent-api-overlay.yaml)
- [Examples](examples/waodao-token-day-1-example.json)
- [Examples](examples/waodao-pools-example.json)
- [Examples](examples/waodao-schema-example.json)
- [JSON Schema](json-schema/waodao-token.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/waodao-index.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/waodao-pools.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/waodao-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/waodao-error.json) — [JSON Schema](https://json-schema.org/specification)
- [Agentic Access](agentic-access/waodao-agentic-access.yml)
- [Domain Security](security/waodao-domain-security.yml)

## Maintainers

**FN:** WAODAO
**Email:** info@waodao.ai
**URL:** https://waodao.ai

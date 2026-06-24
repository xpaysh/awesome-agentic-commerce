# `@xpaysh/*` packages (npm)

The maintainer of this list ([xpay✦](https://www.xpay.sh)) publishes a framework-agnostic npm package family for ACP / UCP / AP2 implementation. Schema-vendored, tested against canonical upstream schemas; the test fixtures themselves ship as a package.

Listed here, not in the main `README.md`, because they are one maintainer's packages rather than a neutral curation. They earn a slot in this repo because they are the only public packages doing schema-vendored validation across all three protocols, with cross-validating fixtures.

| Package | What it does |
|---|---|
| [`@xpaysh/acp-schemas`](https://www.npmjs.com/package/@xpaysh/acp-schemas) | ACP JSON Schemas vendored from the upstream released spec, pinned to a dated version |
| [`@xpaysh/ucp-schemas`](https://www.npmjs.com/package/@xpaysh/ucp-schemas) | UCP schemas vendored from upstream + `generateUcpProfile()` + `registerForValidation(ajv)` |
| [`@xpaysh/ap2-schemas`](https://www.npmjs.com/package/@xpaysh/ap2-schemas) | AP2 namespace (`SPEC_VERSION='draft'` until upstream cuts a stable tag) |
| [`@xpaysh/adapter-contract`](https://www.npmjs.com/package/@xpaysh/adapter-contract) | The `PlatformAdapter` TS interface every per-platform plugin implements |
| [`@xpaysh/template-adapter`](https://www.npmjs.com/package/@xpaysh/template-adapter) | Reference `PlatformAdapter` backed by a deterministic in-memory catalog. Starting point for new plugins. |
| [`@xpaysh/discovery`](https://www.npmjs.com/package/@xpaysh/discovery) | Pure-function generators for `/llms.txt`, schema.org JSON-LD, `robots.txt`, A2A `agent-card.json`, RFC 9728. Zero deps. |
| [`@xpaysh/cart-deeplinks`](https://www.npmjs.com/package/@xpaysh/cart-deeplinks) | HS256-signed JWT cart-handoff URLs |
| [`@xpaysh/storefront-audit`](https://www.npmjs.com/package/@xpaysh/storefront-audit) | Discovery-layer auditor + `ac-doctor` CLI; rejects fictitious well-known URIs |
| [`@xpaysh/http-message-signatures`](https://www.npmjs.com/package/@xpaysh/http-message-signatures) | RFC 9421 sign/verify; ed25519 + hmac-sha256; targets the component set UCP REST uses |
| [`@xpaysh/conformance-fixtures`](https://www.npmjs.com/package/@xpaysh/conformance-fixtures) | Golden ACP + UCP request/response payloads; every fixture cross-validates via Ajv |
| [`@xpaysh/acp-session-store`](https://www.npmjs.com/package/@xpaysh/acp-session-store) | ACP checkout-session storage behind one interface; InMemorySessionStore + DynamoDBSessionStore |
| [`@xpaysh/lint-wellknowns`](https://www.npmjs.com/package/@xpaysh/lint-wellknowns) | CI linter + GitHub Action that fails builds emitting fictitious well-known URIs |

If you publish a parallel package family (Python, Go, Rust) doing the same job against upstream schemas, open a PR adding a sibling file or a section here.

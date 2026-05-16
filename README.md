# Awesome Agentic Commerce

> Curated index of open-source plugins, libraries, and reference implementations for **agentic commerce** — the layer where AI agents (ChatGPT, Claude, Gemini, custom) interact with merchant storefronts on behalf of human buyers.

Covers the active protocols ([ACP](https://github.com/agentic-commerce-protocol/agentic-commerce-protocol), [UCP](https://github.com/Universal-Commerce-Protocol/ucp), [AP2](https://github.com/google-agentic-commerce/AP2)), the discovery standards ([llms.txt](https://llmstxt.org), [A2A agent-card](https://a2a-protocol.org/), schema.org JSON-LD), the payment rails ([MPP](https://mpp.dev), [x402](https://x402.org), cards, stablecoins), and the per-platform integrations that tie them together.

Maintained by [xpay✦](https://www.xpay.sh). PRs welcome.

## Contents

- [Protocols](#protocols)
- [Per-platform plugins](#per-platform-plugins)
- [Reference implementations & SDKs](#reference-implementations--sdks)
- [Payment rails for agents](#payment-rails-for-agents)
- [Discovery standards](#discovery-standards)
- [Conformance & tooling](#conformance--tooling)
- [Related curated lists](#related-curated-lists)

---

## Protocols

| Protocol | Spec | Sponsor | Surface |
|---|---|---|---|
| **ACP** — Agentic Commerce Protocol | [agentic-commerce-protocol/agentic-commerce-protocol](https://github.com/agentic-commerce-protocol/agentic-commerce-protocol) | OpenAI · Stripe · Meta (TSC) | Cart, checkout, delegated payment, discounts, fulfillment |
| **UCP** — Universal Commerce Protocol | [Universal-Commerce-Protocol/ucp](https://github.com/Universal-Commerce-Protocol/ucp) | Tech Council + Governance Council (vendor-neutral) | Cart, checkout, order, catalog, refunds, disputes — RFC 9421 signed requests, MCP/A2A bindings |
| **AP2** — Agent Payments Protocol | [google-agentic-commerce/AP2](https://github.com/google-agentic-commerce/AP2) | Google | Signed mandates, A2A transport |
| Forter's TACP — Trusted Agentic Commerce | [forter/trusted-agentic-commerce-protocol](https://github.com/forter/trusted-agentic-commerce-protocol) | Forter | Fork of ACP with trust extensions |

Side-by-side technical comparison: **[docs.xpay.sh — ACP vs UCP vs AP2](https://docs.xpay.sh/agentic-commerce-protocols/comparison)**.

---

## Per-platform plugins

Each row: which protocols it speaks, license, and link.

### WooCommerce

- **[xpaysh/agentic-commerce-for-woocommerce](https://github.com/xpaysh/agentic-commerce-for-woocommerce)** — ACP + UCP + AP2 (planned). WordPress plugin. GPLv2.

### commercetools

- **[xpaysh/agentic-commerce-for-commercetools](https://github.com/xpaysh/agentic-commerce-for-commercetools)** — Phase B-1, scaffold in progress.

### BigCommerce

- *No dedicated repo yet. Planned: [xpaysh/agentic-commerce-for-bigcommerce](https://github.com/xpaysh/agentic-commerce-for-bigcommerce) (Phase B-2).*

### Magento / Adobe Commerce

- *No dedicated unified repo. Two small ACP modules exist on GitHub (28★, 13★, both unmaintained). Planned consolidation: [xpaysh/agentic-commerce-for-magento](https://github.com/xpaysh/agentic-commerce-for-magento) (Phase B-3).*

### Shopify

- **[Shopify/Shopify-AI-Toolkit](https://github.com/Shopify)** *(name approximate)* — official Shopify AI/UCP path. Vendor-maintained.
- *Planned (differentiated, App-Store distribution): [xpaysh/agentic-commerce-for-shopify-app](https://github.com/xpaysh/agentic-commerce-for-shopify-app) (Phase B-4).*

### Salesforce Commerce Cloud / Demandware

- *No dedicated repo yet. Planned: [xpaysh/agentic-commerce-for-salesforce-commerce](https://github.com/xpaysh/agentic-commerce-for-salesforce-commerce) (Phase B-5).*

### Saleor

- **[saleor/saleor-mcp](https://github.com/saleor)** — official Saleor MCP server.
- *Planned multi-protocol port: [xpaysh/agentic-commerce-for-saleor](https://github.com/xpaysh/agentic-commerce-for-saleor) (Phase C).*

### PrestaShop, OpenCart, Shopware, Spree, Sylius, nopCommerce, Drupal Commerce, Ecwid

*Phase C — template + community PR. See the [contributor guide](https://docs.xpay.sh/merchants/agentic-commerce/contribute) (TBD) and the [plugin template](https://github.com/xpaysh/agentic-commerce-plugin-template).*

---

## Reference implementations & SDKs

- **[vercel/acp-handler](https://github.com/vercel/acp-handler)** — generic Next.js handler for ACP. Platform-agnostic.
- **[NVIDIA-AI-Blueprints/Retail-Agentic-Commerce](https://github.com/NVIDIA-AI-Blueprints/Retail-Agentic-Commerce)** — NVIDIA blueprint covering ACP + UCP.
- **[Universal-Commerce-Protocol/js-sdk](https://github.com/Universal-Commerce-Protocol/js-sdk)** — official UCP TypeScript SDK with RFC 9421 verifier.
- **[Universal-Commerce-Protocol/python-sdk](https://github.com/Universal-Commerce-Protocol/python-sdk)** — official UCP Python SDK.
- **[Universal-Commerce-Protocol/ucp-schema](https://github.com/Universal-Commerce-Protocol/ucp-schema)** — Rust validator.
- **[xpaysh/agentic-commerce-plugin-template](https://github.com/xpaysh/agentic-commerce-plugin-template)** — TypeScript template for new per-platform plugins.

---

## Payment rails for agents

These sit *below* the commerce protocols. Any commerce protocol can plug into any rail.

- **[Stripe MPP](https://mpp.dev)** — Machine Payments Protocol. Cards, stablecoins, fiat acceptance.
- **[x402](https://x402.org)** — HTTP 402 payment rail. Stablecoin settlement.
- **Cards** — Stripe, Adyen, Braintree, etc.
- **Stablecoin direct** — Bridge, Tempo, Privy.

---

## Discovery standards

Real, externally-verifiable standards (no invented well-known URIs):

- **[llmstxt.org](https://llmstxt.org)** — `/llms.txt`, Markdown, LLM-readable site map. Use this.
- **[a2a-protocol.org](https://a2a-protocol.org/)** — `/.well-known/agent-card.json` (A2A 1.0, IANA-registered 2025-08-01).
- **[schema.org](https://schema.org)** — JSON-LD `Product`, `Offer`, `AggregateOffer`, `BreadcrumbList`.
- **[RFC 9309](https://datatracker.ietf.org/doc/rfc9309/)** — `robots.txt`. Real AI user-agents to allowlist or block: `GPTBot`, `ClaudeBot`, `Google-Extended`, `PerplexityBot`, `CCBot`, `Amazonbot`.
- **[RFC 9728](https://datatracker.ietf.org/doc/rfc9728/)** — `/.well-known/oauth-protected-resource` for agent OAuth.

### Files to **not** emit

`/.well-known/agentic-commerce.json`, `/.well-known/ucp.json`, `/.well-known/acp.json`, `/.well-known/ap2.json`, `/.well-known/mcp.json`, `/.well-known/ai-plugin.json` (deprecated), `/agents.txt`, `/ai.txt` — none of these are in any active spec. If you see a plugin emitting one of these, please [open an issue](https://github.com/xpaysh/awesome-agentic-commerce/issues).

---

## Conformance & tooling

- **[Universal-Commerce-Protocol/conformance](https://github.com/Universal-Commerce-Protocol/conformance)** — UCP conformance suite.
- **[Universal-Commerce-Protocol/samples](https://github.com/Universal-Commerce-Protocol/samples)** — sample agents & merchants.

---

## Related curated lists

- **[Awesome MCP Servers](https://github.com/punkpeye/awesome-mcp-servers)** — sister ecosystem; many entries are MCP servers exposed by commerce platforms.
- **[xpaysh/awesome-agentic-economy](https://github.com/xpaysh/awesome-agentic-economy)** — broader: agentic-economy resources (monetization, identity, payment).
- **[Awesome x402](https://github.com/xpaysh-awesome-fork)** — x402-specific resources.

---

## Contributing

This list aims for **signal over volume**. Submit a plugin if it:

1. Implements at least one of ACP / UCP / AP2 against a real eCommerce platform.
2. Emits real-standard discovery files (`llms.txt`, schema.org JSON-LD) and does **not** emit fictitious well-known URIs.
3. Is actively maintained (commit within the last 90 days) OR is the only known plugin for that platform.

Open a PR adding your repo to the relevant section. We sort by last-commit-date within each platform.

## License

[CC0 1.0 Universal](https://creativecommons.org/publicdomain/zero/1.0/) — public domain dedication. Use this list freely.

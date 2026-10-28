# Morapay

**Stablecoins and local rails for merchants** — hosted checkout, collections, payouts, and developer APIs with platform-managed settlement.

Morapay is building payment infrastructure for businesses that need to accept crypto and settle to fiat (and the reverse). Our platform covers merchant onboarding, payment links and hosted checkout, webhooks, disbursements to banks and mobile money, operational oversight, and integration tooling for engineering teams.

> **Note:** Morapay’s application source code is maintained in **private repositories** for security, compliance, and commercial reasons. This repository is our **public overview** for grant reviewers, partners, auditors, integrators, and other stakeholders who need visibility into what we build and how to request deeper access.

## What we build

Morapay is a **merchant payments platform** with a hosted checkout experience, merchant dashboard, and REST APIs. Capabilities vary by country, rail, and account mode (TEST vs LIVE).

| Area | Description |
|------|-------------|
| **Checkout & collections** | Hosted checkout and embeddable flows; customers pay with supported stablecoins and assets across configured chains |
| **Payment links & commerce** | Payment links, carts, products, subscriptions, and fiat-priced invoices with crypto settlement |
| **Payouts & disbursements** | Merchant withdrawals and payouts to bank accounts and mobile money where enabled, with platform routing and operational controls |
| **On- & off-ramp (merchant)** | Quote and execute ramp flows for eligible merchants (onramp/offramp APIs and dashboard tooling where enabled) |
| **Onboarding & compliance** | Business (KYB) and identity workflows, verification providers, and review tooling for platform operators |
| **Developer platform** | API keys (TEST/LIVE), HMAC-signed requests, webhooks, SDKs, and published documentation |
| **Operations** | Admin console for merchants, transactions, settlements, provider configuration, platform wallets, and support workflows |

## How it works (high level)

1. **Onboard & verify** — Businesses sign up, complete KYB where required, and receive API keys and dashboard access.
2. **Create a payment** — Merchants create payment links or server-side charges; customers complete payment on **checkout.morapay.io** (or embedded widget).
3. **Settle & reconcile** — Morapay tracks payment status, applies fees, updates merchant balances, and emits webhooks to the merchant’s systems.
4. **Payout** — Merchants request withdrawals; the platform routes delivery through configured fiat and liquidity partners with operational oversight.

## Platform principles

- **Compliance-aware design** — Verification workflows, audit-friendly transaction records, and operator review paths for high-risk actions.
- **Platform-mediated money movement** — Settlement and payouts run through Morapay’s controlled flows and partner rails, not direct peer settlement between unrelated merchants.
- **TEST before LIVE** — Separate TEST and LIVE API keys; integrators are expected to validate webhooks and payout behavior in TEST first.
- **Security by design** — Secrets stay server-side; checkout and dashboard surfaces integrate wallet and identity providers under strict configuration.
- **Operational transparency** — Authorized platform operators can oversee transactions, settlements, and provider health.

## Technology overview

Morapay is developed as a **TypeScript** system spanning API services, background workers, and web applications. At a high level:

| Layer | Technologies |
|-------|----------------|
| **Customer & merchant web** | Next.js (checkout, marketing, docs, merchant dashboard), Turborepo monorepo |
| **Core API & workers** | Node.js, Fastify, background jobs (BullMQ), structured logging |
| **Edge / BFF** | Node backend for browser-facing proxies and partner callbacks |
| **Data** | PostgreSQL (Prisma), Redis (caching, queues, rate limits) |
| **Realtime** | Webhooks to merchants; realtime UI updates where configured |
| **Integrations** | Identity/KYB providers, fiat and mobile-money rails, liquidity and swap aggregators, email and notifications, blockchain indexing where required |
| **Quality** | TypeScript, ESLint, unit and integration tests, CI on critical paths |

We do **not** publish implementation details, infrastructure diagrams, credentials, or production architecture in this repository.

## Public resources

| Resource | URL |
|----------|-----|
| Website | https://morapay.io |
| Merchant dashboard | https://business.morapay.io |
| Developer documentation | https://docs.morapay.io |
| API (production) | https://api.morapay.io |
| Hosted checkout | https://checkout.morapay.io |
| X (Twitter) | https://x.com/morapay |

### Public GitHub repositories

| Repository | Description |
|------------|-------------|
| [docs](https://github.com/morapay-app/docs) | Developer documentation (Mintlify source) |
| [sdk-examples](https://github.com/morapay-app/sdk-examples) | Sample integrations for the Merchant API |
| [mobile](https://github.com/morapay-app/mobile) | Morapay mobile application |

Private repositories in this account include **core**, **backend**, **dashboard**, **SDK packages**, and **web applications** maintained by the Morapay engineering team.

## Source code access

Our production codebase is **private**. We routinely share materials with:

- Grant and funding reviewers  
- Prospective partners and enterprise merchants  
- Compliance and security auditors  
- Academic or research collaborators (under NDA where required)

### Request access

Email **support@morapay.io** with:

| Field | Details |
|-------|---------|
| **Subject** | GitHub / Code Review Access Request |
| **Your name & affiliation** | Organization, program, or role |
| **Purpose** | e.g. grant review, partnership diligence, security audit, integration architecture review |
| **Scope needed** | Architecture overview, demo environment, read-only repo access, technical walkthrough |
| **Timeline** | Review deadline or preferred dates |

For time-sensitive grant deadlines, include the date in your subject line.

Access may be provided as:

- A guided product demo or staging environment  
- Architecture and product documentation  
- Time-limited, read-only access to private repositories  
- A live technical Q&A session  

All access is subject to confidentiality terms where applicable.

## Security

If you discover a security vulnerability, please **do not** open a public GitHub issue.

Report it responsibly to **security@morapay.io** with the subject **Security Disclosure**.

## Open source

Morapay is a **commercial fintech product**. We rely on open-source dependencies extensively and publish selected documentation and examples in public repositories. This profile repository does **not** imply that the full platform is open source.

## Legal

Information in this repository is provided for **general orientation only**. It does not constitute an offer, solicitation, or financial advice. Product capabilities, availability, fees, and regulatory treatment may vary by jurisdiction, user type, and account configuration.

For terms and privacy information, see **https://morapay.io**.

## Contact

| Channel | Address |
|---------|---------|
| General & access requests | support@morapay.io |
| Security | security@morapay.io |
| Website | https://morapay.io |

© Morapay. All rights reserved.

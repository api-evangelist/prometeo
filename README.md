# Prometeo (prometeo)

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
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Prometeo is a LatAm-founded (Uruguay) fintech infrastructure company offering a single financial API over 7,500+ banking connections across the Americas. Products span banking data access, real-time account validation, cross-border pay-in / payout / FX, account-to-account payments, Mexican CURP identity, and fiscal data (DIAN / SAT / CEP / BCU). All products authenticate with an X-API-Key header and offer a mock-data sandbox.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/prometeo/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/prometeo/refs/heads/main/apis.yml)

## Tags

- Open Banking
- Payments
- FinTech
- LatAm
- Financial Data
- Account Validation
- Cross-Border

## Timestamps

- **Created:** 2026-07-17
- **Modified:** 2026-07-17

## APIs

### Prometeo Banking API

Bank-account access across 7,500+ LatAm banking connections — session login (with MFA), accounts, movements/transactions, credit cards, providers, and account-to-account transfers. Sandbox host `banking.sandbox.prometeoapi.com` uses mock data.

- **Human URL:** [https://docs.prometeoapi.com/docs/3-acceso-a-los-datos](https://docs.prometeoapi.com/docs/3-acceso-a-los-datos)
- **Base URL:** `https://banking.prometeoapi.net`

#### Tags

- Open Banking
- Account Information
- Movements
- Transfers

#### Properties

- [Documentation](https://docs.prometeoapi.com/docs/3-acceso-a-los-datos)
- [API Reference](https://docs.prometeoapi.com/reference/listtransactions-1)
- [OpenAPI](openapi/prometeo-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/prometeo.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)

### Prometeo Account Validation API

Real-time bank account verification confirming an account is valid, reachable, and owned before initiating a transfer or debit, across LatAm markets and the US.

- **Human URL:** [https://prometeoapi.com/en/bank-account-verification](https://prometeoapi.com/en/bank-account-verification)
- **Base URL:** `https://account-validation.prometeoapi.net`

#### Tags

- Account Validation
- Bank Account Verification
- Anti-Fraud

#### Properties

- [API Reference](https://docs.prometeoapi.com/reference/validateaccount)
- [OpenAPI](openapi/prometeo-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/prometeo.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)

### Prometeo Cross-Border Payments API

Cross-border money movement — pay-in intents (virtual accounts / QR), payouts over local rails, FX exchange, customer and withdrawal-account management. Sandbox host `crossborder-api.sandbox.prometeoapi.com`.

- **Human URL:** [https://prometeoapi.com/en/bank-transfer-payments](https://prometeoapi.com/en/bank-transfer-payments)
- **Base URL:** `https://crossborder.secure.prometeoapi.net/v1`

#### Tags

- Cross-Border
- Payouts
- Pay-In
- FX

#### Properties

- [Documentation](https://docs.prometeoapi.com)
- [OpenAPI](openapi/prometeo-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/prometeo.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)

### Prometeo Payment API

Open-banking payment initiation — create and retrieve account-to-account payment intents that move funds directly from a payer's bank account.

- **Human URL:** [https://prometeoapi.com/en/bank-transfer-payments](https://prometeoapi.com/en/bank-transfer-payments)
- **Base URL:** `https://payment.prometeoapi.net`

#### Tags

- Payments
- Account to Account
- Payment Initiation

#### Properties

- [Documentation](https://docs.prometeoapi.com)
- [OpenAPI](openapi/prometeo-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/prometeo.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)

### Prometeo Identity API (CURP)

Mexican CURP identity lookups — query a CURP record by code, or reverse-query a CURP from demographic data for KYC and onboarding.

- **Human URL:** [https://docs.prometeoapi.com](https://docs.prometeoapi.com)
- **Base URL:** `https://identity.prometeoapi.net`

#### Tags

- Identity
- KYC
- CURP
- Mexico

#### Properties

- [Documentation](https://docs.prometeoapi.com)
- [OpenAPI](openapi/prometeo-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/prometeo.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)

### Prometeo Fiscal API

Government / fiscal data access — Colombia DIAN, Mexico SAT and CEP (payment receipt), and Uruguay BCU (central bank) filings and statements. Sandbox host `fiscal.sandbox.prometeoapi.com`.

- **Human URL:** [https://docs.prometeoapi.com](https://docs.prometeoapi.com)
- **Base URL:** `https://fiscal.prometeoapi.net`

#### Tags

- Fiscal
- Tax Data
- DIAN
- SAT
- BCU

#### Properties

- [Documentation](https://docs.prometeoapi.com)

## Authentication

All Prometeo products authenticate the application with a per-account API key sent in the `X-API-Key` request header. Keys are issued from `dashboard.prometeoapi.com`; a mock-data sandbox key is available immediately on first login. The Banking API additionally establishes a per-end-user session — `POST /login/` (optionally answered via `/login-procedure/` for MFA) returns a session `key` passed on subsequent Banking calls. Some services may additionally require mutual TLS (mTLS).

See [authentication/prometeo-authentication.yml](authentication/prometeo-authentication.yml).

## Common Properties

- [GitHub Organization](https://github.com/prometeoapi)
- [LinkedIn](https://www.linkedin.com/company/prometeoapi)
- [Website](https://prometeoapi.com/en)
- [Documentation](https://docs.prometeoapi.com)
- [Plans](plans/prometeo-plans-pricing.yml)
- [Rate Limits](rate-limits/prometeo-rate-limits.yml)
- [Fin Ops](finops/prometeo-finops.yml)
- [Agentic Access](agentic-access/prometeo-agentic-access.yml)
- [Trust Center](security/prometeo-trust-center.yml)
- [Vulnerability Disclosure](security/prometeo-vulnerability-disclosure.yml)
- [Domain Security](security/prometeo-domain-security.yml)
- [Blog](https://prometeoapi.com/en/blog)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com

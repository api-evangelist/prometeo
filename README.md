# Prometeo (prometeo)

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

---
name: Verify a bank account before paying it
description: Confirm a bank account is valid, reachable, and (optionally) owned by a named person before initiating a transfer or debit.
api: openapi/prometeo-openapi.yml
operations: [validateAccount]
host: https://account-validation.prometeoapi.net
sandbox_host: https://account-validation.sandbox.prometeoapi.com
---

# Verify a bank account before paying it

Use this before any payout to reduce failed transfers and fraud.

## Auth
Send your per-account API key in the `X-API-Key` header. No banking session is needed for account validation.

## Steps
1. Call `validateAccount` (`POST /validate-account/`) with a JSON body containing at least `account_number` and `country_code` (ISO code, e.g. `MX`, `BR`, `PE`, `US`); include `bank_code` and `document_number` when you have them for ownership confirmation.
2. Read the validation result to confirm the account is valid and reachable (and, when a document was supplied, that ownership matches).
3. Only proceed to a payout/transfer once the account validates.

## Conventions & errors
- Coverage and rails vary by country (PIX in BR, SPEI in MX, RTP/FedNow in US) - see the docs coverage pages.
- Errors return `{ "status": ..., "message": ... }`; a `401` means a missing/invalid `X-API-Key`.
- Test against `account-validation.sandbox.prometeoapi.com` with mock data first.

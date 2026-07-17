---
name: Stage and confirm an account-to-account transfer
description: Move money from a user's bank account by staging a transfer, handling any MFA, then confirming it.
api: openapi/prometeo-openapi.yml
operations: [login, listTransferDestinations, preprocessTransfer, confirmTransfer]
host: https://banking.prometeoapi.net
sandbox_host: https://banking.sandbox.prometeoapi.com
consequence: physical (moves money)
---

# Stage and confirm an account-to-account transfer

This is a money-movement flow - treat it as safety-critical and confirm intent with the user.

## Auth
`X-API-Key` header + the Banking session `key` from `login` on every call.

## Steps
1. Ensure you have a logged-in session (`login`; see the session skill).
2. Optionally `listTransferDestinations` (`GET /transfer/destinations?key=...`) to pick an enrolled destination account.
3. `preprocessTransfer` (`POST /transfer/preprocess`) with `key`, `origin_account`, `destination_account`, `amount`, `currency` (and `destination_institution`/`concept`). This **stages** the transfer and returns a `request_id`; it may require MFA.
4. `confirmTransfer` (`POST /transfer/confirm`) with the `key` and the staged `request_id` (plus `authorization_type`/`authorization_data` if an MFA answer is required). This is what actually moves the money.

## Conventions & idempotency
- The two-step preprocess -> confirm pattern is the safety control: a confirm replays the `request_id` from preprocess, so you cannot confirm without a prior staged request. Do not re-run `confirmTransfer` with the same `request_id` after success.
- Errors return `{ "status": ..., "message": ... }`.
- Always exercise this in sandbox (`provider=test`) before production.

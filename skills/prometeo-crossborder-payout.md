---
name: Create a cross-border pay-in and pay out over local rails
description: Collect funds via a cross-border pay-in intent, optionally FX-exchange, then pay out over local rails.
api: openapi/prometeo-openapi.yml
operations: [createPayinIntent, getPayinIntent, exchangeFx, createPayout, getPayout]
host: https://crossborder.secure.prometeoapi.net/v1
sandbox_host: https://crossborder-api.sandbox.prometeoapi.com
consequence: physical (moves money)
---

# Create a cross-border pay-in and pay out over local rails

## Auth
Send your `X-API-Key` header. Cross-Border runs under `/v1` on `crossborder.secure.prometeoapi.net`.

## Steps
1. `createPayinIntent` (`POST /payin/intent`) to create a pay-in intent (virtual account / QR) for the payer.
2. Track it with `getPayinIntent` (`GET /payin/intent/{intent_id}`), or wait for the `payin.settled` webhook (see `asyncapi/prometeo-webhooks.yml`) rather than polling.
3. If the payout currency differs, `exchangeFx` (`POST /fx/exchange`) to convert.
4. `createPayout` (`POST /payout/transfer`) to disburse over local rails; confirm with `getPayout` (`GET /payout/transfer/{payout_id}`).

## Conventions & errors
- Prefer the webhook (`verify_token` + `events[].event_id`) over polling; de-duplicate on `event_id`.
- Money-movement operations have no documented Idempotency-Key header - never blindly retry `createPayout`; check status first.
- Errors return `{ "status": ..., "message": ... }`. Test on the sandbox host first.

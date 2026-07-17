---
name: Look up Mexican CURP identity data
description: Query a Mexican CURP record by code, or resolve a CURP from a person's demographic data, for KYC/onboarding.
api: openapi/prometeo-openapi.yml
operations: [curpQuery, curpReverseQuery]
host: https://identity.prometeoapi.net
sandbox_host: https://identity.sandbox.prometeoapi.com
---

# Look up Mexican CURP identity data

## Auth
Send your `X-API-Key` header. No banking session is required.

## Steps
1. If you have the CURP code: `curpQuery` (`POST /query`) with `{ "curp": "<CURP>" }` to return the identity record.
2. If you only have personal data: `curpReverseQuery` (`POST /reverse-query`) with `name`, `first_surname`, `last_surname`, `birthday`, `gender`, `state` to resolve the CURP.

## Conventions & errors
- Errors return `{ "status": ..., "message": ... }`; `401` = missing/invalid `X-API-Key`.
- Exercise on `identity.sandbox.prometeoapi.com` with mock data before production.

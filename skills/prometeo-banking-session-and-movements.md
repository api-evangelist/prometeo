---
name: Open a banking session and read accounts and movements
description: Log a user into their bank (handling MFA), then list their accounts and transaction movements.
api: openapi/prometeo-openapi.yml
operations: [login, loginProcedure, listAccounts, listMovements, logout]
host: https://banking.prometeoapi.net
sandbox_host: https://banking.sandbox.prometeoapi.com
---

# Open a banking session and read accounts and movements

## Auth
Send your `X-API-Key` header on every call. The Banking API also uses a per-user **session key**: `login` returns a `key` you pass as the `key` query parameter on all subsequent Banking calls.

## Steps
1. `login` (`POST /login/`, `application/x-www-form-urlencoded`) with `provider`, `username`, `password`. In sandbox use `provider=test`.
2. Inspect `LoginResponse.status`:
   - `logged_in` -> continue with the returned `key`.
   - `interaction_required` -> answer the MFA challenge with `loginProcedure` (`POST /login-procedure/`) passing the `key` and the user's `answer`, then continue.
   - `wrong_credentials` / `error` -> stop and surface the message.
3. `listAccounts` (`GET /account/?key=...`) to enumerate the user's accounts.
4. `listMovements` (`GET /movement/`) with `key`, `account`, `currency`, and a `date_start`/`date_end` window (`dd/mm/yyyy`).
5. `logout` (`GET /logout/?key=...`) when finished to invalidate the session key.

## Conventions & errors
- Movements are filtered by date window, not a cursor.
- A `401` indicates a missing/invalid `X-API-Key` or an expired session `key`.

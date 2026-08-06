---
name: Drive the 1Fort agent runtime to resolve a business and autofill a draft quote
description: >-
  The agent-native surface. Find or create the business behind an inbound submission, read the
  session's source files, then fill a draft quote from extracted data — the only operations in the
  API that document idempotent re-runs.
api: openapi/1fort-openapi-original.yml
base_url: https://api.1fort.com/apis/
generated: '2026-08-05'
method: generated
operations:
  - v2_broker_agent_businesses_find_list
  - v2_broker_agent_businesses_create
  - v2_broker_agent_businesses_update_create
  - v2_broker_agent_sessions_files_list
  - v2_broker_agent_sessions_files_content_list
  - v2_broker_agent_quotes_read
  - v2_broker_agent_quotes_fill_create
---

# Drive the 1Fort agent runtime

The `agent_runtime (v2)` tag is 1Fort's own machine-facing surface, sitting under
`/v2/broker/agent/...`. It exists so an automated worker can turn an inbound broker submission
(usually an email with attachments, handled by the Email AI Agent) into a filled draft quote.

## Before you start

- `Authorization: Bearer <jwt>`.
- **`X-Processing-Session` is a required header on 23 operations** on this surface — a processing
  session token that scopes access to a broker. You cannot substitute the tenant path id for it.
- These endpoints are broker-scoped, **not** profile-scoped. Do not mix them with the
  `email_ai (v2): profiles` operations without checking which scope each one expects.

## Steps

1. **Resolve the business.** `v2_broker_agent_businesses_find_list`
   (`GET /v2/broker/agent/businesses/find`). If there is no match, create it with
   `v2_broker_agent_businesses_create` (`POST /v2/broker/agent/businesses`); if the match is stale,
   correct it with `v2_broker_agent_businesses_update_create`
   (`POST /v2/broker/agent/businesses/{business_id}/update`).
   Search before you create — there is no dedupe key and no idempotency header.
2. **Read the source documents.** `v2_broker_agent_sessions_files_list`
   (`GET /v2/broker/agent/sessions/{session_pk}/files`) then
   `v2_broker_agent_sessions_files_content_list` (`.../files/{file_pk}/content`) for the extracted
   content of each attachment.
3. **Inspect the draft before filling.** `v2_broker_agent_quotes_read`
   (`GET /v2/broker/agent/quotes/{quote_id}`). 1Fort documents this as the read the runtime uses
   "to inspect what the draft already has before filling, so re-runs stay idempotent."
4. **Fill.** `v2_broker_agent_quotes_fill_create`
   (`POST /v2/broker/agent/quotes/{quote_id}/fill`).

## Rules an agent must follow

- **The only documented idempotency in this API lives here — and it is server-side, not a contract.**
  Two agent-runtime operations describe idempotent re-runs (the draft-quote read-before-fill pattern
  above, and the business-scoped coverage draft create, which "creates the CoverageTerm and
  CoverageApplication only if the draft doesn't already have them"). There is still **no**
  `Idempotency-Key` header anywhere in the API, so this is a property of those handlers, not a
  guarantee you can rely on across other endpoints. Always do step 3 before step 4.
- **Errors on this surface use the newer envelope:** `ErrorResponse {error:{code,message},
  request_id}`. 401 returns `{"error":{"code":"UNAUTHORIZED","message":"..."}}`; 409 means the
  target is already in a terminal state (documented on the v2 broker agent email patch). Log
  `request_id` on every failure — it is the only tracing identifier 1Fort exposes.
- **409 means stop, not retry.** A terminal-state conflict will never succeed on replay.

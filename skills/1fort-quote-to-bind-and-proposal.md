---
name: Compare quotes, build the proposal, and bind
description: >-
  Work returned quotes through to a bound policy — list and read quotes, clear outstanding quote
  tasks, generate the white-labeled proposal PDF, create the bind, and confirm the binder.
api: openapi/1fort-openapi-original.yml
base_url: https://api.1fort.com/apis/
generated: '2026-08-05'
method: generated
operations:
  - v2_broker_quotes_list
  - v2_broker_quotes_read
  - v2_broker_quotes_tasks_list
  - v2_broker_quotes_tasks_create
  - v2_broker_quotes_proposal-content_list
  - v2_broker_quotes_proposal-content_update
  - v2_broker_quotes_proposal-pdf_list
  - v2_applications_download_insurance_proposal_pdf
  - v2_broker_quotes_bind_create
  - v2_broker_quotes_bind_read
  - v2_broker_binders_list
  - v2_broker_binders_read
---

# Compare quotes, build the proposal, and bind

Use this after coverage applications have been submitted and carriers have returned quotes.

## Before you start

- `Authorization: Bearer <jwt>`; tenant-scoped by `business_pk`. Base path `/apis/`.
- Binding is the highest-consequence action in this API. Treat every step from "create bind" onward
  as requiring explicit human confirmation.

## Steps

1. **List quotes for the client.** `v2_broker_quotes_list`
   (`GET /v2/broker/{business_pk}/quotes`). Filter on `status`, `carrier`, `coverage`,
   `effective_date_min` / `effective_date_max`; page with `limit`/`offset`.
2. **Read the one you care about.** `v2_broker_quotes_read`
   (`GET /v2/broker/{business_pk}/quotes/{id}`). Quote documents come back through
   `v2_broker_quotes_get_file` and `v2_broker_quotes_get_surplus_file`.
3. **Clear outstanding quote tasks.** `v2_broker_quotes_tasks_list`
   (`GET /v2/broker/{business_pk}/quotes/{quote_pk}/tasks`) then resolve with
   `v2_broker_quotes_tasks_create` (`POST` the same path). Where the insured has to act, use
   `v2_broker_quotes_tasks_notify_insured_requests`. A carrier will not bind with open subjectivities.
4. **Assemble the proposal.** Read the editable content with
   `v2_broker_quotes_proposal-content_list` (`GET /v2/broker/quotes/{quote_id}/proposal-content/`),
   edit with `v2_broker_quotes_proposal-content_update` (`PUT`), then render with
   `v2_broker_quotes_proposal-pdf_list` (`GET /v2/broker/quotes/{quote_id}/proposal-pdf/`).
   The application-level equivalent is `v2_applications_download_insurance_proposal_pdf`.
5. **Bind — human confirmation required.** `v2_broker_quotes_bind_create`
   (`POST /v2/broker/{business_pk}/quotes/{quote_pk}/bind`). This commits the client to coverage and
   to premium. Never call it autonomously.
6. **Confirm.** `v2_broker_quotes_bind_read`, then `v2_broker_binders_list` /
   `v2_broker_binders_read` (`GET /v2/broker/{business_pk}/binders`) for the binder and
   `v2_broker_binders_get_document` for its documents.

## Rules an agent must follow

- **No idempotency key.** A retried `POST .../bind` is a second bind attempt, not a safe replay.
  On any timeout or 5xx, re-read with `v2_broker_quotes_bind_list` / `v2_broker_quotes_bind_read`
  before doing anything else.
- **500 is declared on every operation** in this spec and carries no body schema. Treat it as
  "state unknown" and reconcile by reading, never by re-posting.
- **No webhooks are available to you.** 1Fort's webhook endpoints are inbound receivers for Stripe,
  Ascend, Herald, Gmail and Office 365 — there is no subscription API for customers. Poll the quote
  and binder list operations for status changes (see `asyncapi/1fort-webhooks.yml`).
- **Deprecated surface to avoid:** all `/ascend/*` and `/v2/ascend/payments/*` operations are flagged
  deprecated. Use `/v2/billing/*` instead (see `lifecycle/1fort-lifecycle.yml`).

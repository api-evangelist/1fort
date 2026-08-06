---
name: Submit a commercial insurance application for quotes
description: >-
  Take a broker's client from an empty application to submitted coverage applications sitting with
  carriers — create the application, generate and prefill the question set, use AI web research to
  fill gaps, check which carriers are relevant, then submit.
api: openapi/1fort-openapi-original.yml
base_url: https://api.1fort.com/apis/
generated: '2026-08-05'
method: generated
operations:
  - v2_broker_clients_list
  - v2_broker_applications_create
  - v2_broker_applications_start_application
  - v2_broker_applications_generate_questions
  - v2_broker_applications_add_prefilled_forms
  - v2_broker_applications_coverages_list
  - v2_broker_coverages_answer_with_ai
  - v2_broker_coverages_answer_with_ai_result
  - v2_broker_applications_get_relevant_carriers
  - v2_broker_coverages_submit
  - v2_broker_applications_submit
  - v2_broker_applications_approve
---

# Submit a commercial insurance application for quotes

Use this when a broker wants quotes for a client across one or more coverage lines.

## Before you start

- Send `Authorization: Bearer <jwt>` on every call. `Api-Key <key>` is the alternative format on the
  same header. See `authentication/1fort-authentication.yml`.
- Everything is tenant-scoped. You need the client's `business_pk`; a token is only authorised for
  the businesses its user may access, and object-level permissions are enforced per endpoint. A 404
  can mean "not found" **or** "you may not see it" — do not treat it as proof the object is absent.
- Base path is `/apis/`. All operations below are `v2`, the current surface.

## Steps

1. **Find the client.** `v2_broker_clients_list` (`GET /v2/broker/clients`). Filter with `search`,
   page with `limit`/`offset`. The client id is the `business_pk` used everywhere below.
2. **Create the application.** `v2_broker_applications_create`
   (`POST /v2/broker/{business_pk}/applications`).
3. **Start it.** `v2_broker_applications_start_application`
   (`POST /v2/broker/{business_pk}/applications/{id}/start`).
4. **Generate the question set.** `v2_broker_applications_generate_questions`
   (`POST /v2/broker/{business_pk}/applications/{id}/generate-questions`).
5. **Prefill what you already know.** `v2_broker_applications_add_prefilled_forms`
   (`POST /v2/broker/{business_pk}/applications/{id}/pre-filled-forms`).
6. **List the coverage applications.** `v2_broker_applications_coverages_list`
   (`GET /v2/broker/{business_pk}/applications/{application_pk}/coverages`). Each coverage is
   submitted independently.
7. **Fill remaining answers with AI research (optional, asynchronous).**
   `v2_broker_coverages_answer_with_ai` (`POST .../coverages/{id}/answer-with-ai`) kicks off web
   research and returns a `task_id`. Poll `v2_broker_coverages_answer_with_ai_result`
   (`GET .../coverages/{id}/answer-with-ai/{task_id}`) until it resolves. This is a
   **write with real-world consequence** — it researches and mutates the application. Do not fire it
   repeatedly while a task is outstanding; there is no idempotency key to protect you (see below).
8. **Check the market fit before submitting.** `v2_broker_applications_get_relevant_carriers`
   (`GET /v2/broker/{business_pk}/applications/{id}/relevant-carriers`).
9. **Submit.** Either per coverage with `v2_broker_coverages_submit`
   (`POST .../coverages/{id}/submit`), or all eligible coverages at once with
   `v2_broker_applications_submit` (`POST /v2/broker/{business_pk}/applications/{id}/submit`).
10. **Release anything held for broker review.** `v2_broker_applications_approve`
    (`POST /v2/broker/{business_pk}/applications/{id}/approve`) approves all coverage applications
    held for the broker; `v2_broker_coverages_approve` does one.

## Rules an agent must follow

- **No idempotency key exists.** None of the 574 operations accept an `Idempotency-Key`. A retried
  `submit` or `create` may duplicate work at a carrier. Confirm state with the matching `read`/`list`
  operation before retrying a write, and never retry a submit blindly on a timeout.
- **Errors.** 403 → `GenericError {detail}`; 404 → `APIException {detail}` (may be a permission mask);
  400 → `ValidationError`, a field-keyed map of message arrays plus `non_field_errors`. Newer v2
  agent endpoints return `ErrorResponse {error:{code,message}, request_id}` — log `request_id`.
  No 429 is declared anywhere, so back off on your own signal. See `errors/1fort-problem-types.yml`.
- **Pagination** is `limit`/`offset` with `count`/`next`/`previous`/`results`. There is no cursor.
- **Submitting is not reversible from the API.** There is no unsubmit operation. Treat step 9 as the
  point of no return and confirm with the human broker first.

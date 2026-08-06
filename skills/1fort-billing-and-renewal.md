---
name: Reconcile billing and renew a policy
description: >-
  The post-bind servicing loop — read the billing dashboard and payments backed by insurance
  invoices, pull Stripe receipts, check refunds, then renew an expiring policy off its quote policy.
api: openapi/1fort-openapi-original.yml
base_url: https://api.1fort.com/apis/
generated: '2026-08-05'
method: generated
operations:
  - v2_billing_payments_stats
  - v2_billing_payments_list
  - v2_billing_payments_read
  - v2_billing_payments_stripe_receipt
  - v2_billing_refunds_list
  - v2_broker_quote-policies_list
  - v2_broker_quote-policies_read
  - v2_broker_quote-policies_renew_application
---

# Reconcile billing and renew a policy

## Before you start

- `Authorization: Bearer <jwt>`. Base path `/apis/`.
- **Use `/v2/billing/*`, not `/ascend/*`.** Every v1 `/ascend/*` operation and the whole
  `/v2/ascend/payments/*` group are flagged `deprecated: true` in the published spec — 17 operations
  in total, all of them the Ascend premium-finance payables rails. `lifecycle/1fort-lifecycle.yml`
  lists them. No Sunset header and no removal date is published, so the flag is the only warning
  you get.

## Billing

1. **Dashboard.** `v2_billing_payments_stats` (`GET /v2/billing/payments/stats`) — payments at risk,
   invoices and policies needing attention.
2. **List payments.** `v2_billing_payments_list` (`GET /v2/billing/payments`), backed by insurance
   invoices. Filter with `status` / `payment_status`, page with `limit`/`offset`. Discover the valid
   filter values from `v2_billing_payments_filter_options` rather than guessing. A CSV mirror of the
   same filters is at `v2_billing_payments_export_csv`.
3. **Read one.** `v2_billing_payments_read`, and pull the processor receipt with
   `v2_billing_payments_stripe_receipt` (`GET /v2/billing/payments/{id}/stripe-receipt`).
   1Fort settles card and ACH through Stripe.
4. **Refunds.** `v2_billing_refunds_list` (`GET /v2/billing/refunds`) — refunded checkout payments
   against the broker's insurance invoices.

## Renewal

5. **Find the expiring policy.** `v2_broker_quote-policies_list`
   (`GET /v2/broker/{business_pk}/quote-policies`), then `v2_broker_quote-policies_read`. Policy
   documents come from `v2_broker_quote-policies_get_document`.
6. **Renew — human confirmation required.** `v2_broker_quote-policies_renew_application`
   (`POST /v2/broker/{business_pk}/quote-policies/{id}/renew`). This opens a new application from
   the expiring policy. Hand off to `1fort-submit-application-for-quotes.md` from there.

## Rules an agent must follow

- **Money operations have no idempotency key.** `v2_billing_payments_partial_update` and the renew
  call cannot be safely replayed. On a timeout, re-read before acting.
- **No 429 and no rate-limit headers are declared.** Only four invite operations publish a limit
  (10/min). Self-throttle on bulk list/CSV pulls.
- **Never surface a raw `detail` string to an end customer** — 403 and 404 bodies are used
  interchangeably for "missing" and "not permitted".

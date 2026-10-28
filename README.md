# 1Fort

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

1Fort is a New York City based insurtech platform that automates the commercial insurance workflow for brokers and agencies. Its AI "copilot" autofills submissions across 300+ coverages, quotes direct and wholesale markets, generates white-labeled proposals with side-by-side coverage comparisons and cross-sell recommendations, then processes binders, invoicing, premium finance, payments and payables through to ongoing policy servicing. Coverage lines span cyber, technology errors and omissions, professional liability, management liability, general liability and workers compensation. The platform runs on AWS, holds SOC 2 Type II, HIPAA and CCPA attestations, and exposes a large REST API at api.1fort.com whose Swagger 2.0 definition is published publicly at /api-docs — 574 operations across broker, application, quote, market, billing, checkout, storefront and Email AI Agent surfaces, plus inbound webhook receivers for Stripe, Ascend, Herald, Gmail and Office 365.

**Areas:** Insurance · Insurtech · Commercial Insurance · Cyber Insurance · Insurance Broker · Quoting · Policy Management · premium-finance · Payments · Workflow Automation · Artificial Intelligence · AI Agents

## 1Fort on APIs.io

Everything profiled for 1Fort is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/1fort/](https://apis.io/providers/1fort/)** — or go straight to one of the APIs or properties below.

### APIs (89)

- [1Fort agent_runtime (v2) API](https://apis.io/apis/1fort/1fort-agent-runtime-v2-api/) — **Access:** requires a JWT access token.
- [1Fort Analytics API](https://apis.io/apis/1fort/1fort-analytics-api/) — **Access:** requires a JWT access token.
- [1Fort application: applications API](https://apis.io/apis/1fort/1fort-application-applications-api/) — **Access:** requires a JWT access token.
- [1Fort application: clients API](https://apis.io/apis/1fort/1fort-application-clients-api/) — **Access:** requires a JWT access token.
- [1Fort application (v2): applications API](https://apis.io/apis/1fort/1fort-application-v2-applications-api/) — **Access:** requires a JWT access token.
- [1Fort application (v2): coverages API](https://apis.io/apis/1fort/1fort-application-v2-coverages-api/) — **Access:** requires a JWT access token.
- [1Fort Ascend API](https://apis.io/apis/1fort/1fort-ascend-api/) — **Deprecated.** Legacy Ascend billing/payments; use the Billing (v2) endpoints instead. **Access:** mixed; some endpoints are public, others require JWT or…
- [1Fort ascend (v2) API](https://apis.io/apis/1fort/1fort-ascend-v2-api/) — **Deprecated.** Legacy Ascend billing/payments; use the Billing (v2) endpoints instead. **Access:** requires a JWT access token.
- [1Fort Auth API](https://apis.io/apis/1fort/1fort-auth-api/) — Sign in / sign up via Google or Office365 OAuth and refresh JWT access tokens. **Access:** mixed; some endpoints are public, others require JWT (per endpoint).
- [1Fort Authentication API](https://apis.io/apis/1fort/1fort-authentication-api/) — One-time-password (OTP) authentication. **Access:** public; no authentication required.
- [1Fort billing (v2) API](https://apis.io/apis/1fort/1fort-billing-v2-api/) — Billing and payments. Replaces the deprecated Ascend payment endpoints. **Access:** requires a JWT access token.
- [1Fort broker: ai-customization-types API](https://apis.io/apis/1fort/1fort-broker-ai-customization-types-api/) — **Access:** requires a JWT access token.
- [1Fort broker: ai-customizations API](https://apis.io/apis/1fort/1fort-broker-ai-customizations-api/) — **Access:** requires a JWT access token.
- [1Fort Broker Ams Integration API](https://apis.io/apis/1fort/1fort-broker-ams-integration-api/) — **Access:** requires a JWT access token.
- [1Fort Broker API](https://apis.io/apis/1fort/1fort-broker-api/) — **Access:** mixed; some endpoints are public, others require JWT (per endpoint).
- [1Fort broker: clients API](https://apis.io/apis/1fort/1fort-broker-clients-api/) — **Access:** requires a JWT access token.
- [1Fort broker: email_preferences API](https://apis.io/apis/1fort/1fort-broker-email-preferences-api/) — **Access:** requires a JWT access token.
- [1Fort Broker Google API](https://apis.io/apis/1fort/1fort-broker-google-api/) — **Access:** public; no authentication required.
- [1Fort Broker Groups API](https://apis.io/apis/1fort/1fort-broker-groups-api/) — **Access:** requires a JWT access token.
- [1Fort Broker Office365 API](https://apis.io/apis/1fort/1fort-broker-office365-api/) — **Access:** public; no authentication required.
- [1Fort Broker Office365 Individual API](https://apis.io/apis/1fort/1fort-broker-office365-individual-api/) — **Access:** public; no authentication required.
- [1Fort broker: proposal-preferences API](https://apis.io/apis/1fort/1fort-broker-proposal-preferences-api/) — **Access:** requires a JWT access token.
- [1Fort Broker Settings API](https://apis.io/apis/1fort/1fort-broker-settings-api/) — **Access:** requires a JWT access token.
- [1Fort broker: take-rates API](https://apis.io/apis/1fort/1fort-broker-take-rates-api/) — **Access:** requires a JWT access token.
- [1Fort broker: user-ai-customizations API](https://apis.io/apis/1fort/1fort-broker-user-ai-customizations-api/) — **Access:** requires a JWT access token.
- [1Fort broker: users API](https://apis.io/apis/1fort/1fort-broker-users-api/) — **Access:** requires a JWT access token.
- [1Fort broker (v2): applications API](https://apis.io/apis/1fort/1fort-broker-v2-applications-api/) — **Access:** requires a JWT access token.
- [1Fort broker (v2): clients API](https://apis.io/apis/1fort/1fort-broker-v2-clients-api/) — **Access:** requires a JWT access token.
- [1Fort broker (v2): coverages API](https://apis.io/apis/1fort/1fort-broker-v2-coverages-api/) — **Access:** requires a JWT access token.
- [1Fort broker (v2): email-templates API](https://apis.io/apis/1fort/1fort-broker-v2-email-templates-api/) — **Access:** requires a JWT access token.
- [1Fort broker (v2): quote-policies API](https://apis.io/apis/1fort/1fort-broker-v2-quote-policies-api/) — **Access:** requires a JWT access token.
- [1Fort broker (v2): quotes API](https://apis.io/apis/1fort/1fort-broker-v2-quotes-api/) — **Access:** requires a JWT access token.
- [1Fort broker (v2): storefront API](https://apis.io/apis/1fort/1fort-broker-v2-storefront-api/) — **Access:** requires a JWT access token.
- [1Fort broker (v2): team-users API](https://apis.io/apis/1fort/1fort-broker-v2-team-users-api/) — **Access:** requires a JWT access token.
- [1Fort Business Admin API](https://apis.io/apis/1fort/1fort-business-admin-api/) — **Access:** requires a JWT access token.
- [1Fort Business API](https://apis.io/apis/1fort/1fort-business-api/) — **Access:** requires a JWT access token.
- [1Fort Business Broker Users API](https://apis.io/apis/1fort/1fort-business-broker-users-api/) — **Access:** requires a JWT access token.
- [1Fort Business User API](https://apis.io/apis/1fort/1fort-business-user-api/) — **Access:** requires a JWT access token.
- [1Fort Carrier API](https://apis.io/apis/1fort/1fort-carrier-api/) — **Access:** requires a JWT access token.
- [1Fort Checkout API](https://apis.io/apis/1fort/1fort-checkout-api/) — Checkout and payment session endpoints. **Access:** public; no authentication required.
- [1Fort Email AI Agent API](https://apis.io/apis/1fort/1fort-email-ai-agent-api/) — **Access:** requires a JWT access token.
- [1Fort Email AI Agent - Attachments API](https://apis.io/apis/1fort/1fort-email-ai-agent-attachments-api/) — **Access:** requires a JWT access token.
- [1Fort Email AI Agent - Businesses API](https://apis.io/apis/1fort/1fort-email-ai-agent-businesses-api/) — **Access:** requires a JWT access token.
- [1Fort Email AI Agent - Entities API](https://apis.io/apis/1fort/1fort-email-ai-agent-entities-api/) — **Access:** requires a JWT access token.
- [1Fort Email AI Agent - Markets API](https://apis.io/apis/1fort/1fort-email-ai-agent-markets-api/) — **Access:** requires a JWT access token.
- [1Fort Email AI Agent - Profiles API](https://apis.io/apis/1fort/1fort-email-ai-agent-profiles-api/) — **Access:** requires a JWT access token.
- [1Fort Email AI Agent - Reference Data API](https://apis.io/apis/1fort/1fort-email-ai-agent-reference-data-api/) — **Access:** requires a JWT access token.
- [1Fort Email AI API](https://apis.io/apis/1fort/1fort-email-ai-api/) — **Access:** requires a JWT access token.
- [1Fort email_ai (v2): attachments API](https://apis.io/apis/1fort/1fort-email-ai-v2-attachments-api/) — **Access:** requires a JWT access token.
- [1Fort email_ai (v2): carriers API](https://apis.io/apis/1fort/1fort-email-ai-v2-carriers-api/) — **Access:** requires a JWT access token.
- [1Fort email_ai (v2): coverage-types API](https://apis.io/apis/1fort/1fort-email-ai-v2-coverage-types-api/) — **Access:** requires a JWT access token.
- [1Fort email_ai (v2): emails API](https://apis.io/apis/1fort/1fort-email-ai-v2-emails-api/) — **Access:** requires a JWT access token.
- [1Fort email_ai (v2): gmail API](https://apis.io/apis/1fort/1fort-email-ai-v2-gmail-api/) — **Access:** public; no authentication required.
- [1Fort email_ai (v2): office365 API](https://apis.io/apis/1fort/1fort-email-ai-v2-office365-api/) — **Access:** public; no authentication required.
- [1Fort email_ai (v2): profiles API](https://apis.io/apis/1fort/1fort-email-ai-v2-profiles-api/) — **Access:** requires a JWT access token.
- [1Fort email_ai (v2): wholesalers API](https://apis.io/apis/1fort/1fort-email-ai-v2-wholesalers-api/) — **Access:** requires a JWT access token.
- [1Fort google_workspace (v2) API](https://apis.io/apis/1fort/1fort-google-workspace-v2-api/) — **Access:** requires a JWT access token.
- [1Fort herald (v2) API](https://apis.io/apis/1fort/1fort-herald-v2-api/) — **Access:** mixed; some endpoints are public, others require JWT or an API key (per endpoint).
- [1Fort indications (v2) API](https://apis.io/apis/1fort/1fort-indications-v2-api/) — **Access:** requires a JWT access token.
- [1Fort insurance (v2) API](https://apis.io/apis/1fort/1fort-insurance-v2-api/) — **Access:** requires a JWT access token.
- [1Fort Invite API](https://apis.io/apis/1fort/1fort-invite-api/) — Invitations for broker and business users. **Access:** mixed; some endpoints are public, others require JWT (per endpoint).
- [1Fort Legal API](https://apis.io/apis/1fort/1fort-legal-api/) — Legal documents and agreements. **Access:** requires a JWT access token.
- [1Fort market (v2) API](https://apis.io/apis/1fort/1fort-market-v2-api/) — **Access:** requires a JWT access token.
- [1Fort Markets API](https://apis.io/apis/1fort/1fort-markets-api/) — **Access:** requires a JWT access token.
- [1Fort Markets - Business API](https://apis.io/apis/1fort/1fort-markets-business-api/) — **Access:** requires a JWT access token.
- [1Fort office365 (v2) API](https://apis.io/apis/1fort/1fort-office365-v2-api/) — **Access:** requires a JWT access token.
- [1Fort premium_finance (v2) API](https://apis.io/apis/1fort/1fort-premium-finance-v2-api/) — **Access:** requires a JWT access token.
- [1Fort quote_ai (v2) API](https://apis.io/apis/1fort/1fort-quote-ai-v2-api/) — **Access:** requires a JWT access token.
- [1Fort quote: applications API](https://apis.io/apis/1fort/1fort-quote-applications-api/) — **Access:** requires a JWT access token.
- [1Fort quote: clients API](https://apis.io/apis/1fort/1fort-quote-clients-api/) — **Access:** requires a JWT access token.
- [1Fort quote: quotes API](https://apis.io/apis/1fort/1fort-quote-quotes-api/) — **Access:** requires a JWT access token.
- [1Fort quote (v2): application API](https://apis.io/apis/1fort/1fort-quote-v2-application-api/) — **Access:** requires a JWT access token.
- [1Fort quote (v2): binders API](https://apis.io/apis/1fort/1fort-quote-v2-binders-api/) — **Access:** requires a JWT access token.
- [1Fort quote (v2): checkout API](https://apis.io/apis/1fort/1fort-quote-v2-checkout-api/) — **Access:** public; no authentication required.
- [1Fort quote (v2): cios API](https://apis.io/apis/1fort/1fort-quote-v2-cios-api/) — **Access:** requires a JWT access token.
- [1Fort quote (v2): coverages API](https://apis.io/apis/1fort/1fort-quote-v2-coverages-api/) — **Access:** requires a JWT access token.
- [1Fort quote (v2): quote-policies API](https://apis.io/apis/1fort/1fort-quote-v2-quote-policies-api/) — **Access:** requires a JWT access token.
- [1Fort quote (v2): quotes API](https://apis.io/apis/1fort/1fort-quote-v2-quotes-api/) — **Access:** requires a JWT access token.
- [1Fort quote (v2): tasks API](https://apis.io/apis/1fort/1fort-quote-v2-tasks-api/) — **Access:** requires a JWT access token.
- [1Fort Reports API](https://apis.io/apis/1fort/1fort-reports-api/) — **Access:** requires a JWT access token.
- [1Fort Reward API](https://apis.io/apis/1fort/1fort-reward-api/) — **Access:** requires a JWT access token.
- [1Fort Risk Manager API](https://apis.io/apis/1fort/1fort-risk-manager-api/) — **Access:** requires a JWT access token.
- [1Fort Sanity Check AI API](https://apis.io/apis/1fort/1fort-sanity-check-ai-api/) — **Access:** requires a JWT access token.
- [1Fort storefront (v2) API](https://apis.io/apis/1fort/1fort-storefront-v2-api/) — Insured-facing storefront endpoints. Access is scoped by storefront identity (public links, API key, or storefront permission) rather than a user JWT.…
- [1Fort Stripe API](https://apis.io/apis/1fort/1fort-stripe-api/) — **Access:** mixed; some endpoints are public, others require JWT (per endpoint).
- [1Fort Suggestion AI API](https://apis.io/apis/1fort/1fort-suggestion-ai-api/) — **Access:** requires a JWT access token or an API key.
- [1Fort treasury (v2) API](https://apis.io/apis/1fort/1fort-treasury-v2-api/) — **Access:** requires a JWT access token.
- [1Fort User API](https://apis.io/apis/1fort/1fort-user-api/) — **Access:** requires a JWT access token.
- [1Fort user: default-access-role API](https://apis.io/apis/1fort/1fort-user-default-access-role-api/) — **Access:** requires a JWT access token.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [1Fort Webhooks](https://apis.io/asyncapis/1fort/1fort-webhooks/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [1fort](https://apis.io/servers/1fort/1fort/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [1Fort Agentic Access](https://apis.io/agentic-access/1fort/1fort-agentic-access/)

#### Collections (89)

Postman and Open Collection request collections.

- [1Fort API Documentation agent_runtime (v2) agent_runtime (v2) API](https://apis.io/collections/1fort/open-1fort-agent-runtime-v2-api/)
- [1Fort API Documentation Analytics API](https://apis.io/collections/1fort/open-1fort-analytics-api/)
- [1Fort API Documentation application: applications API](https://apis.io/collections/1fort/open-1fort-application-applications-api/)
- [1Fort API Documentation application: clients API](https://apis.io/collections/1fort/open-1fort-application-clients-api/)
- [1Fort API Documentation application (v2): applications API](https://apis.io/collections/1fort/open-1fort-application-v2-applications-api/)
- [1Fort API Documentation application (v2): coverages API](https://apis.io/collections/1fort/open-1fort-application-v2-coverages-api/)
- [1Fort API Documentation Ascend API](https://apis.io/collections/1fort/open-1fort-ascend-api/)
- [1Fort API Documentation ascend (v2) ascend (v2) API](https://apis.io/collections/1fort/open-1fort-ascend-v2-api/)
- [1Fort API Documentation Auth API](https://apis.io/collections/1fort/open-1fort-auth-api/)
- [1Fort API Documentation Authentication API](https://apis.io/collections/1fort/open-1fort-authentication-api/)
- [1Fort API Documentation billing (v2) billing (v2) API](https://apis.io/collections/1fort/open-1fort-billing-v2-api/)
- [1Fort API Documentation broker: ai-customization-types API](https://apis.io/collections/1fort/open-1fort-broker-ai-customization-types-api/)
- [1Fort API Documentation broker: ai-customizations API](https://apis.io/collections/1fort/open-1fort-broker-ai-customizations-api/)
- [1Fort API Documentation Broker Ams Integration API](https://apis.io/collections/1fort/open-1fort-broker-ams-integration-api/)
- [1Fort API Documentation Broker API](https://apis.io/collections/1fort/open-1fort-broker-api/)
- [1Fort API Documentation broker: clients API](https://apis.io/collections/1fort/open-1fort-broker-clients-api/)
- [1Fort API Documentation broker: email_preferences API](https://apis.io/collections/1fort/open-1fort-broker-email-preferences-api/)
- [1Fort API Documentation Broker Google API](https://apis.io/collections/1fort/open-1fort-broker-google-api/)
- [1Fort API Documentation Broker Groups API](https://apis.io/collections/1fort/open-1fort-broker-groups-api/)
- [1Fort API Documentation Broker Office365 API](https://apis.io/collections/1fort/open-1fort-broker-office365-api/)
- [1Fort API Documentation Broker Office365 Individual API](https://apis.io/collections/1fort/open-1fort-broker-office365-individual-api/)
- [1Fort API Documentation broker: proposal-preferences API](https://apis.io/collections/1fort/open-1fort-broker-proposal-preferences-api/)
- [1Fort API Documentation Broker Settings API](https://apis.io/collections/1fort/open-1fort-broker-settings-api/)
- [1Fort API Documentation broker: take-rates API](https://apis.io/collections/1fort/open-1fort-broker-take-rates-api/)
- [1Fort API Documentation broker: user-ai-customizations API](https://apis.io/collections/1fort/open-1fort-broker-user-ai-customizations-api/)
- …and 64 more published on APIs.io

#### Overlays (1)

OpenAPI overlays, including conversational phrasing for each operation.

- [1Fort Openapi Overlay](https://apis.io/overlays/1fort/1fort-openapi-overlay/)

#### Security (4)

Authentication, trust centre, and vulnerability disclosure.

- [1Fort Authentication](https://apis.io/security/1fort/1fort-authentication/)
- [1Fort Domain Security](https://apis.io/security/1fort/1fort-domain-security/)
- [1Fort Trust Center](https://apis.io/security/1fort/1fort-trust-center/)
- [1Fort Vulnerability Disclosure](https://apis.io/security/1fort/1fort-vulnerability-disclosure/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [1Fort Plans Pricing](https://apis.io/plans/1fort/1fort-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [1Fort Rate Limits](https://apis.io/rate-limits/1fort/1fort-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://1fort.ai/)
- [Documentation](https://api.1fort.com/api-docs)
- [API reference](https://api.1fort.com/api-docs)
- [Pricing](https://1fort.ai/pricing)
- [Sign up](https://1fort.ai/demo)
- [Support](https://help.1fort.com/en/)
- [Blog](https://1fort.ai/blog)
- [Security](https://1fort.ai/security)
- [Compliance](https://security.1fort.com/)
- [Terms of service](https://1fort.ai/terms-conditions)
- [Privacy policy](https://1fort.ai/privacy)
- [Status](https://status.1fort.com/)

## API Evangelist rating

**Kin Score 64.5** — strong · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 73.2 |
| Contract quality | 56.7 |
| Contract governance | 18.2 |
| Operational transparency | 50.0 |
| Developer ergonomics | 37.5 |
| Access clarity | 92.1 |

**Agent readiness 31.6** — agent-ready

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | documented (partial credit) |
| MCP Server | — |
| Auth Clarity | bearer (partial credit) |
| Idempotency | — |
| Error Semantics | verified |
| OpenAPI Examples | partial |
| Rate Limit Signal | derived (partial credit) |
| Event Surface Described | derived (partial credit) |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | paginated |
| Operation Distinctiveness | — |

**Regulatory alignment 29.5** — Insurance

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/1fort/](https://apis.io/providers/1fort/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for 1Fort: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/1fort/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).

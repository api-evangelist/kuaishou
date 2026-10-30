# Kuaishou

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

Kuaishou Technology (快手) is a Beijing-based short-video and live-streaming platform operating Kuaishou in mainland China and Kwai internationally, spanning short video, live commerce, local services and online marketing. Its developer surface is split across two public properties: the Kuaishou Open Platform (open.kuaishou.com), which exposes an OAuth 2.0 authorization-code flow and a JSON Open API for third-party apps, mini programs and merchant integrations; and Kwai for Business (developers.kwai.com), the international marketing/advertising API used by advertisers and measurement partners. A third and markedly more open surface is Kling AI (kling.ai), Kuaishou's generative video and image platform, which ships an asynchronous REST API, an official CLI, a hosted MCP server with published OAuth scopes, and the only llms.txt Kuaishou serves anywhere. Kuaishou also publishes open source under the Kwai GitHub organization. The Open Platform console and the Kwai for Business portal are JavaScript single-page applications, largely Chinese-language and gated behind developer registration, but the mini-program documentation subtree at open.kuaishou.com/docs is server-rendered and publicly readable, so this profile records endpoints and pages verified by live HTTP probe or read from that subtree.

**Areas:** Company · Consumer · Social · Video · Short Video · Live Streaming · Advertising · Marketing · Social Media · Content · China · Artificial Intelligence

## Kuaishou on APIs.io

Everything profiled for Kuaishou is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/kuaishou/](https://apis.io/providers/kuaishou/)** — or go straight to one of the APIs or properties below.

### APIs (3)

- [Kuaishou Open Platform API](https://apis.io/apis/kuaishou/open-platform/) — The Kuaishou Open Platform (快手开放平台) exposes a JSON HTTP API for third-party applications, mini programs and merchant tools built on Kuaishou. Access is…
- [Kwai for Business Marketing API](https://apis.io/apis/kuaishou/kwai-for-business/) — Kwai for Business is Kuaishou's international advertising and marketing platform for the Kwai app. Its developer portal at developers.kwai.com documents a…
- [Kling AI API](https://apis.io/apis/kuaishou/kling-ai/) — Kling AI (可灵) is Kuaishou Technology's generative video and image platform, launched in June 2024 and, by the company's own account, responsible for over…

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [Kling AI MCP Server](https://apis.io/servers/kuaishou/kling-ai-mcp-server/)

#### Security (2)

Authentication, trust centre, and vulnerability disclosure.

- [Kuaishou Authentication](https://apis.io/security/kuaishou/kuaishou-authentication/)
- [Kuaishou Domain Security](https://apis.io/security/kuaishou/kuaishou-domain-security/)

#### OAuth scopes (1)

The permissions the API asks for.

- [Kuaishou Scopes](https://apis.io/scopes/kuaishou/kuaishou-scopes/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Kuaishou Plans Pricing](https://apis.io/plans/kuaishou/kuaishou-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Kuaishou Rate Limits](https://apis.io/rate-limits/kuaishou/kuaishou-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.kuaishou.com/)
- [Documentation](https://open.kuaishou.com/docs)
- [Getting started](https://open.kuaishou.com/docs/introduction/quickStartGuide/quickStart.html)
- [API reference](https://open.kuaishou.com/docs/develop/server/code2Session.html)
- [Pricing](https://kling.ai/dev/pricing)
- [Support](https://www.kuaishou.com/about/contact)
- [Blog](https://kling.ai/blog)
- [Terms of service](https://www.kuaishou.com/about/policy?tab=protocol)
- [Privacy policy](https://www.kuaishou.com/about/policy?tab=privacy)
- [GitHub](https://github.com/kwai)

## API Evangelist rating

**Kin Score 29.6** — thin · rubric 0.24.0 · scored 2026-10-17

| Facet | Score |
|---|---|
| Discoverability | 76.7 |
| Contract quality | 0.0 |
| Contract governance | 4.5 |
| Operational transparency | 18.4 |
| Developer ergonomics | 63.7 |
| Access clarity | 21.1 |

**Agent readiness 28.5** — agent-aware

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | — |
| Agentic Access | — |
| Reversibility Documented | — |
| MCP Server | documented (partial credit) |
| Auth Clarity | served (partial credit) |
| Idempotency | — |
| Error Semantics | documented (partial credit) |
| OpenAPI Examples | — |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | — |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | served (partial credit) |
| Protected Resource Metadata | verified |
| Dynamic Client Registration | yes |
| Agentic Commerce | — |

**Regulatory alignment 31.8** — AI & Biometrics

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/kuaishou/](https://apis.io/providers/kuaishou/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Kuaishou: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/kuaishou/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).

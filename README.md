# NAIC (naic)

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

The National Association of Insurance Commissioners (NAIC) is the U.S. standard-setting and regulatory support organization created and governed by the chief insurance regulators of the 50 states, the District of Columbia and five territories. It is not a carrier and not a federal regulator — under the McCarran-Ferguson settlement the United States has no national insurance supervisor, so the NAIC is the coordinating body through which state-based regulation is made uniform. It writes the model laws, accounting practices and Annual Statement Blanks that every admitted insurer files against, operates the Financial Data Repository behind those filings, and runs the market infrastructure the industry actually transacts on: SERFF for electronic rate and form filing, State Based Systems (SBS) for producer and company licensing in roughly thirty jurisdictions, iSite+ and myNAIC for regulator analytics, OPTins for premium tax, and consumer-facing lookups such as the Consumer Information Source and the Life Insurance Policy Locator. Its lines of business span property and casualty, life and annuity, health, title and fraternal across the United States.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/naic/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/naic/refs/heads/main/apis.yml)

## Tags

- Insurance
- United States
- Regulator
- Market Infrastructure
- Insurance Regulation
- Property and Casualty
- Life Insurance
- Health Insurance
- Producer Licensing
- Rate and Form Filing
- Regulatory Reporting
- Standards Body

## Timestamps

- **Created:** 2026-07-25
- **Modified:** 2026-07-25

## API Posture

The NAIC publishes **no public developer portal and no documented self-serve API**. Probed on 2026-07-25:

- `developer.naic.org`, `developers.naic.org`, `docs.naic.org` — all NXDOMAIN
- `api.naic.org` — resolves and answers over HTTP/2, but returns a bare `text/plain` `Not Found` on `/`, `/openapi.json`, `/swagger.json`, `/api-docs`, `/v1`, `/docs`, `/health`, `/swagger-ui.html` and `/actuator`. An internal gateway, not a portal.
- `content.naic.org/developers`, `/api`, `/apis`, `/developer`, `/web-services`, `/data` — all HTTP 404

**Zero OpenAPI, Swagger, WSDL or AsyncAPI documents were found.** The NAIC publishes no specification of any kind.

The only API-shaped surface the NAIC *names* in public is **SERFF Web Services**, and it is partner-gated. Everything else — myNAIC, iSite+, SBS, OPTins, SERFF Login — is an Okta-fronted web application. Bulk regulatory data from the Financial Data Repository is licensed by contract (`idp@naic.org`) and delivered as CSV; InsData sells statutory financial statements as PDFs. Neither is an API.

### …but there is an undocumented one

The 2026-07-25 enrichment round probed `content.naic.org` itself rather than only the developer-hostname candidates, and found a **live, anonymously readable JSON:API v1.1** at [`https://content.naic.org/jsonapi`](https://content.naic.org/jsonapi), served by Drupal 11. Its entry point returns a machine-readable resource index enumerating **284 resource types**, and anonymous `GET` returns HTTP 200 `application/vnd.api+json` across every content family. It carries the NAIC's model law corpus (with MDL model numbers), the state insurance department regulator directory, committees and task forces, insurance topics, publications, CIPR research, the newsroom, and the published PDFs behind them.

The NAIC has never advertised it. There is no documentation, no changelog, no deprecation policy, no status page and no support channel scoped to it — and the underlying Drupal content model is unversioned. Treat it as a **real but unsupported public read surface**.

The NAIC also publishes a first-party [`llms.txt`](https://content.naic.org/llms.txt) declaring AI usage preferences (`allow_model_training: false`, `require_attribution: true`), crawl guidance (`crawl_delay: 10`, `max_requests_per_day: 100`) and path scoping — so its stated contract with automated consumers is more explicit than its contract with API developers. **Honor it; nothing enforces it server-side.**

The `openapi/` document in this repo is **derived by API Evangelist** from that live resource index (`x-publisher-provided: false`), not published by the NAIC.

### ACORD posture

**No ACORD reference found.** A full-text scan of the official [NAIC Technology Products and Services Catalog](https://content.naic.org/sites/default/files/naic-technology-services-products-catalog.pdf) (57,226 characters extracted) returned **zero** occurrences of `ACORD`, `XML`, `web service`, `REST`, `SOAP` or `developer`. The NAIC runs its own statutory idiom — Annual Statement Blanks, the Market Conduct Annual Statement (MCAS), risk-based capital reporting, and the SERFF filing schema — which sits parallel to ACORD rather than mapping onto it. No AL3, NGDS, IVANS or agency-download reference exists in the NAIC estate.

## APIs

### SERFF Web Services

The NAIC-operated SERFF (System for Electronic Rates & Forms Filing) platform exposes machine integration services to filers, state regulators and filing vendors. The SERFF Technical Support Checklist published at serff.com names three services by name — Legacy SPI (two-way PUSH/PULL), Legacy SIS (one-way PULL), and a Modernized Data API (one-way PULL) — each available in PROD and BETA environments. There is **no public reference documentation, no OpenAPI or WSDL, and no self-serve signup**: access is provisioned by request to `wsrequest@naic.org` and the service hosts are credential-gated (`services.serff.com` returned HTTP 403 anonymously; `services-beta.serff.com` returned HTTP 200 but serves only an NAIC/NIPR landing page). Recorded here as a real but partner-gated surface, not a public API.

- **Human URL:** [https://www.serff.com/](https://www.serff.com/)

#### Tags

- Insurance
- Rate and Form Filing
- Regulatory Reporting
- Partner Gated

#### Properties

- [Documentation](https://www.serff.com/)
- [Documentation](https://www.serff.com/documents/serff-services-support-checklist.pdf) — SERFF Technical Support Checklist
- [Documentation](https://www.serff.com/serff_modernization.htm) — SERFF Modernization

### NAIC Content JSON:API

A live, anonymously readable **JSON:API v1.1** surface over the NAIC's public regulatory content estate, served by Drupal 11 and **undocumented by the publisher**. Supports the full JSON:API query grammar — sparse fieldsets, filtering, sorting, relationship inclusion, offset pagination capped at 50 — and returns JSON:API error objects rather than RFC 9457 problem details. Writes are closed (`POST` → HTTP 401 *"No authentication credentials provided."*, `DELETE` → 405). It carries the **content** estate only: **not** SERFF filings, the Financial Data Repository, SBS licensing or OPTins.

- **Base URL:** `https://content.naic.org/jsonapi`
- **Human URL:** [https://content.naic.org/](https://content.naic.org/)
- **Auth:** none — anonymous read

#### Properties

- [OpenAPI](openapi/naic-content-jsonapi-openapi.yml) — **derived**, 569 operations
- [Examples](examples/_index.yml) — five verbatim live payloads
- [Documentation](https://jsonapi.org/format/1.1/) — the JSON:API specification the surface implements

## Artifacts in this repo

| Artifact | File | Method |
|---|---|---|
| OpenAPI | [`openapi/naic-content-jsonapi-openapi.yml`](openapi/naic-content-jsonapi-openapi.yml) | derived from the live resource index |
| llms.txt | [`llms/naic-llms.txt`](llms/naic-llms.txt) | **searched** — publisher-authored, verbatim |
| Examples | [`examples/`](examples/) | **searched** — five verbatim live responses |
| Conventions | [`conventions/naic-conventions.yml`](conventions/naic-conventions.yml) | derived from live probes |
| Error catalog | [`errors/naic-problem-types.yml`](errors/naic-problem-types.yml) | derived from provoked live errors |
| Data model | [`data-model/naic-data-model.yml`](data-model/naic-data-model.yml) | derived |
| Authentication | [`authentication/naic-authentication.yml`](authentication/naic-authentication.yml) | searched |
| Conformance | [`conformance/naic-conformance.yml`](conformance/naic-conformance.yml) | derived |
| Lifecycle | [`lifecycle/naic-lifecycle.yml`](lifecycle/naic-lifecycle.yml) | searched |
| Well-known | [`well-known/naic-well-known.yml`](well-known/naic-well-known.yml) | searched — audited **negative** record |
| Domain security | [`security/naic-domain-security.yml`](security/naic-domain-security.yml) | probed |
| MCP server | [`mcp/naic-mcp.yml`](mcp/naic-mcp.yml) | derived — **candidate**, nothing deployed |
| Agent skills | [`skills/`](skills/) | generated — 3 skills, grounded operationIds |
| Agentic access | [`agentic-access/naic-agentic-access.yml`](agentic-access/naic-agentic-access.yml) | generated — 569 read-only contracts |

**Not present, because they genuinely do not exist:** SDKs/packages, CLI, sandbox, changelog, status page, deprecation policy, webhooks/AsyncAPI, GraphQL, gRPC, OAuth scopes, Postman collection, security.txt, vulnerability-disclosure program, trust center, GitHub organization.

## Common Properties

- [Website](https://content.naic.org/)
- [About](https://content.naic.org/about)
- [Newsroom](https://content.naic.org/newsroom)
- [Insurance Topics](https://content.naic.org/insurance-topics)
- [Publications](https://content.naic.org/publications)
- [SERFF](https://www.serff.com/)
- [State Based Systems (SBS)](https://sbs.naic.org/)
- [iSite+](https://isiteplus.naic.org/iSiteUI/faces/pages/Home.xhtml)
- [InsData](https://insdata.naic.org/)
- [Financial Data Repository](https://content.naic.org/insurance-topics/financial-data-repository)
- [Consumer Information Source](https://content.naic.org/cis_consumer_information.htm)
- [Technology Products and Services Catalog](https://content.naic.org/sites/default/files/naic-technology-services-products-catalog.pdf)
- [Contact / Support](https://content.naic.org/contact)
- [Help](https://content.naic.org/help)
- [Terms & Conditions](https://content.naic.org/application/terms-conditions)
- [Privacy Statement](https://content.naic.org/privacy_statement.htm)

## Related but distinct

**NIPR** (the National Insurance Producer Registry, [nipr.com](https://www.nipr.com)) is a separate legal entity from the NAIC even though the two share systems and branding. Any producer-licensing API activity belongs on the NIPR record, not this one.

## Maintainers

- Kin Lane — kin@apievangelist.com

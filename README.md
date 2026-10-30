# NAIC

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

The National Association of Insurance Commissioners (NAIC) is the U.S. standard-setting and regulatory support organization created and governed by the chief insurance regulators of the 50 states, the District of Columbia and five territories. It is not a carrier and not a federal regulator - under the McCarran-Ferguson settlement the United States has no national insurance supervisor, so the NAIC is the coordinating body through which state-based regulation is made uniform. It writes the model laws, accounting practices and Annual Statement Blanks that every admitted insurer files against, operates the Financial Data Repository behind those filings, and runs the market infrastructure the industry actually transacts on: SERFF for electronic rate and form filing, State Based Systems (SBS) for producer and company licensing in roughly thirty jurisdictions, iSite+ and myNAIC for regulator analytics, OPTins for premium tax, and consumer-facing lookups such as the Consumer Information Source and the Life Insurance Policy Locator. Its lines of business span property and casualty, life and annuity, health, title and fraternal across the United States. Its API posture is partner-gated and closed: there is no developer portal at developer/developers/docs.naic.org (all NXDOMAIN), no documented self-serve API, and no downloadable OpenAPI anywhere on naic.org or serff.com. SERFF does operate real integration services - Legacy SPI (two-way PUSH/PULL), Legacy SIS (one-way PULL) and a Modernized Data API (one-way PULL), in PROD and BETA - but they are named only on a support checklist, provisioned by emailing wsrequest@naic.org, and fronted by Okta login walls. Bulk regulatory data is licensed by contract through idp@naic.org rather than served over an API. There is, however, one real and entirely undocumented public machine surface: content.naic.org runs Drupal 11 and serves a live, anonymously readable JSON:API v1.1 at /jsonapi, whose resource index enumerates 284 resource types and exposes the model law corpus with its MDL numbers, the state insurance department regulator directory, committees, insurance topics, publications, CIPR research and the newsroom. The NAIC also publishes a first-party llms.txt declaring AI usage preferences, attribution requirements and crawl limits - so its stated contract with automated consumers is more explicit than its contract with API developers.

**Areas:** Insurance · United States · Regulator · Market Infrastructure · Insurance Regulation · Property and Casualty · Life Insurance · Health Insurance · Producer Licensing · Rate and Form Filing · Regulatory Reporting · Standards Body

## NAIC on APIs.io

Everything profiled for NAIC is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/naic/](https://apis.io/providers/naic/)** — or go straight to one of the APIs or properties below.

### APIs (73)

- [SERFF Web Services](https://apis.io/apis/naic/serff-web-services/) — The NAIC-operated SERFF (System for Electronic Rates & Forms Filing) platform exposes machine integration services to filers, state regulators and filing…
- [NAIC Action API](https://apis.io/apis/naic/naic-action-api/) — action entity resources exposed by the NAIC JSON:API.
- [NAIC Base Field Override API](https://apis.io/apis/naic/naic-base-field-override-api/) — base_field_override entity resources exposed by the NAIC JSON:API.
- [NAIC Block API](https://apis.io/apis/naic/naic-block-api/) — block entity resources exposed by the NAIC JSON:API.
- [NAIC Block Content API](https://apis.io/apis/naic/naic-block-content-api/) — Reusable content blocks used to compose NAIC pages.
- [NAIC Block Content Type API](https://apis.io/apis/naic/naic-block-content-type-api/) — block_content_type entity resources exposed by the NAIC JSON:API.
- [NAIC Classy Paragraphs Style API](https://apis.io/apis/naic/naic-classy-paragraphs-style-api/) — classy_paragraphs_style entity resources exposed by the NAIC JSON:API.
- [NAIC Comment API](https://apis.io/apis/naic/naic-comment-api/) — Comment entities.
- [NAIC Comment Type API](https://apis.io/apis/naic/naic-comment-type-api/) — comment_type entity resources exposed by the NAIC JSON:API.
- [NAIC Config Pages API](https://apis.io/apis/naic/naic-config-pages-api/) — Site-wide configuration content, including the sitewide alert.
- [NAIC Config Pages Type API](https://apis.io/apis/naic/naic-config-pages-type-api/) — config_pages_type entity resources exposed by the NAIC JSON:API.
- [NAIC Configurable Language API](https://apis.io/apis/naic/naic-configurable-language-api/) — configurable_language entity resources exposed by the NAIC JSON:API.
- [NAIC Crop API](https://apis.io/apis/naic/naic-crop-api/) — crop entity resources exposed by the NAIC JSON:API.
- [NAIC Crop Type API](https://apis.io/apis/naic/naic-crop-type-api/) — crop_type entity resources exposed by the NAIC JSON:API.
- [NAIC Date Format API](https://apis.io/apis/naic/naic-date-format-api/) — date_format entity resources exposed by the NAIC JSON:API.
- [NAIC Discovery API](https://apis.io/apis/naic/naic-discovery-api/) — The JSON:API entry point.
- [NAIC Editor API](https://apis.io/apis/naic/naic-editor-api/) — editor entity resources exposed by the NAIC JSON:API.
- [NAIC Embed Button API](https://apis.io/apis/naic/naic-embed-button-api/) — embed_button entity resources exposed by the NAIC JSON:API.
- [NAIC Entity Browser API](https://apis.io/apis/naic/naic-entity-browser-api/) — entity_browser entity resources exposed by the NAIC JSON:API.
- [NAIC Entity Extra Field API](https://apis.io/apis/naic/naic-entity-extra-field-api/) — entity_extra_field entity resources exposed by the NAIC JSON:API.
- [NAIC Entity Form Display API](https://apis.io/apis/naic/naic-entity-form-display-api/) — entity_form_display entity resources exposed by the NAIC JSON:API.
- [NAIC Entity Form Mode API](https://apis.io/apis/naic/naic-entity-form-mode-api/) — entity_form_mode entity resources exposed by the NAIC JSON:API.
- [NAIC Entity View Display API](https://apis.io/apis/naic/naic-entity-view-display-api/) — entity_view_display entity resources exposed by the NAIC JSON:API.
- [NAIC Entity View Mode API](https://apis.io/apis/naic/naic-entity-view-mode-api/) — entity_view_mode entity resources exposed by the NAIC JSON:API.
- [NAIC Event Entity API](https://apis.io/apis/naic/naic-event-entity-api/) — Event entities.
- [NAIC Feeds Feed API](https://apis.io/apis/naic/naic-feeds-feed-api/) — Feeds importer configuration for state contacts, departments and meeting calendars.
- [NAIC Feeds Feed Type API](https://apis.io/apis/naic/naic-feeds-feed-type-api/) — feeds_feed_type entity resources exposed by the NAIC JSON:API.
- [NAIC Feeds Subscription API](https://apis.io/apis/naic/naic-feeds-subscription-api/) — feeds_subscription entity resources exposed by the NAIC JSON:API.
- [NAIC Field Config API](https://apis.io/apis/naic/naic-field-config-api/) — field_config entity resources exposed by the NAIC JSON:API.
- [NAIC Field Storage Config API](https://apis.io/apis/naic/naic-field-storage-config-api/) — field_storage_config entity resources exposed by the NAIC JSON:API.
- [NAIC File API](https://apis.io/apis/naic/naic-file-api/) — Uploaded file entities backing the media entities.
- [NAIC Filter Format API](https://apis.io/apis/naic/naic-filter-format-api/) — filter_format entity resources exposed by the NAIC JSON:API.
- [NAIC Image Style API](https://apis.io/apis/naic/naic-image-style-api/) — image_style entity resources exposed by the NAIC JSON:API.
- [NAIC Imce Profile API](https://apis.io/apis/naic/naic-imce-profile-api/) — imce_profile entity resources exposed by the NAIC JSON:API.
- [NAIC Language Content Settings API](https://apis.io/apis/naic/naic-language-content-settings-api/) — language_content_settings entity resources exposed by the NAIC JSON:API.
- [NAIC Layout Builder Browser Block API](https://apis.io/apis/naic/naic-layout-builder-browser-block-api/) — layout_builder_browser_block entity resources exposed by the NAIC JSON:API.
- [NAIC Layout Builder Browser Blockcat API](https://apis.io/apis/naic/naic-layout-builder-browser-blockcat-api/) — layout_builder_browser_blockcat entity resources exposed by the NAIC JSON:API.
- [NAIC Linkit Profile API](https://apis.io/apis/naic/naic-linkit-profile-api/) — linkit_profile entity resources exposed by the NAIC JSON:API.
- [NAIC Media API](https://apis.io/apis/naic/naic-media-api/) — Media entities — documents (PDF publications, reports), images, video and audio.
- [NAIC Media Type API](https://apis.io/apis/naic/naic-media-type-api/) — media_type entity resources exposed by the NAIC JSON:API.
- [NAIC Menu API](https://apis.io/apis/naic/naic-menu-api/) — menu entity resources exposed by the NAIC JSON:API.
- [NAIC Menu Link Content API](https://apis.io/apis/naic/naic-menu-link-content-api/) — Site navigation menu links.
- [NAIC Metatag Defaults API](https://apis.io/apis/naic/naic-metatag-defaults-api/) — metatag_defaults entity resources exposed by the NAIC JSON:API.
- [NAIC Node API](https://apis.io/apis/naic/naic-node-api/) — Drupal content nodes — the NAIC's articles, committee pages, publications pages, state insurance department contacts, newsletters, calendars and generic pages.
- [NAIC Node Type API](https://apis.io/apis/naic/naic-node-type-api/) — node_type entity resources exposed by the NAIC JSON:API.
- [NAIC Paragraph API](https://apis.io/apis/naic/naic-paragraph-api/) — Paragraph entities — the composable page building blocks.
- [NAIC Paragraphs Type API](https://apis.io/apis/naic/naic-paragraphs-type-api/) — paragraphs_type entity resources exposed by the NAIC JSON:API.
- [NAIC Path Alias API](https://apis.io/apis/naic/naic-path-alias-api/) — path_alias entity resources exposed by the NAIC JSON:API.
- [NAIC Pathauto Pattern API](https://apis.io/apis/naic/naic-pathauto-pattern-api/) — pathauto_pattern entity resources exposed by the NAIC JSON:API.
- [NAIC Print Engine API](https://apis.io/apis/naic/naic-print-engine-api/) — print_engine entity resources exposed by the NAIC JSON:API.
- [NAIC Rdf Mapping API](https://apis.io/apis/naic/naic-rdf-mapping-api/) — rdf_mapping entity resources exposed by the NAIC JSON:API.
- [NAIC Redirect API](https://apis.io/apis/naic/naic-redirect-api/) — redirect entity resources exposed by the NAIC JSON:API.
- [NAIC Rest Resource Config API](https://apis.io/apis/naic/naic-rest-resource-config-api/) — rest_resource_config entity resources exposed by the NAIC JSON:API.
- [NAIC Search API Index API](https://apis.io/apis/naic/naic-search-api-index-api/) — search_api_index entity resources exposed by the NAIC JSON:API.
- [NAIC Search API Server API](https://apis.io/apis/naic/naic-search-api-server-api/) — search_api_server entity resources exposed by the NAIC JSON:API.
- [NAIC Search API Task API](https://apis.io/apis/naic/naic-search-api-task-api/) — search_api_task entity resources exposed by the NAIC JSON:API.
- [NAIC Settings API](https://apis.io/apis/naic/naic-settings-api/) — settings entity resources exposed by the NAIC JSON:API.
- [NAIC Shortcut API](https://apis.io/apis/naic/naic-shortcut-api/) — shortcut entity resources exposed by the NAIC JSON:API.
- [NAIC Shortcut Set API](https://apis.io/apis/naic/naic-shortcut-set-api/) — shortcut_set entity resources exposed by the NAIC JSON:API.
- [NAIC Simple Sitemap API](https://apis.io/apis/naic/naic-simple-sitemap-api/) — simple_sitemap entity resources exposed by the NAIC JSON:API.
- [NAIC Simple Sitemap Engine API](https://apis.io/apis/naic/naic-simple-sitemap-engine-api/) — simple_sitemap_engine entity resources exposed by the NAIC JSON:API.
- [NAIC Simple Sitemap Type API](https://apis.io/apis/naic/naic-simple-sitemap-type-api/) — simple_sitemap_type entity resources exposed by the NAIC JSON:API.
- [NAIC Slick API](https://apis.io/apis/naic/naic-slick-api/) — slick entity resources exposed by the NAIC JSON:API.
- [NAIC Taxonomy Term API](https://apis.io/apis/naic/naic-taxonomy-term-api/) — Controlled vocabularies — model laws, insurance types, states, committees, publications, research topics and the rest of the NAIC's classification terms.
- [NAIC Taxonomy Vocabulary API](https://apis.io/apis/naic/naic-taxonomy-vocabulary-api/) — taxonomy_vocabulary entity resources exposed by the NAIC JSON:API.
- [NAIC Toolbar Menu Element API](https://apis.io/apis/naic/naic-toolbar-menu-element-api/) — toolbar_menu_element entity resources exposed by the NAIC JSON:API.
- [NAIC User API](https://apis.io/apis/naic/naic-user-api/) — User entities (public fields only for anonymous callers).
- [NAIC User Role API](https://apis.io/apis/naic/naic-user-role-api/) — user_role entity resources exposed by the NAIC JSON:API.
- [NAIC View API](https://apis.io/apis/naic/naic-view-api/) — view entity resources exposed by the NAIC JSON:API.
- [NAIC Webform API](https://apis.io/apis/naic/naic-webform-api/) — webform entity resources exposed by the NAIC JSON:API.
- [NAIC Webform Options API](https://apis.io/apis/naic/naic-webform-options-api/) — webform_options entity resources exposed by the NAIC JSON:API.
- [NAIC Webform Submission API](https://apis.io/apis/naic/naic-webform-submission-api/) — webform_submission entity resources exposed by the NAIC JSON:API.
- [NAIC Workflow API](https://apis.io/apis/naic/naic-workflow-api/) — workflow entity resources exposed by the NAIC JSON:API.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [naic](https://apis.io/servers/naic/naic/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Naic Agentic Access](https://apis.io/agentic-access/naic/naic-agentic-access/)

#### Examples (5)

Example requests and responses.

- [Naic Jsonapi Resource Index](https://apis.io/examples/naic/naic-jsonapi-resource-index/)
- [Naic Node Article Example](https://apis.io/examples/naic/naic-node-article-example/)
- [Naic Node State Department Contact Example](https://apis.io/examples/naic/naic-node-state-department-contact-example/)
- [Naic Taxonomy Model Law Example](https://apis.io/examples/naic/naic-taxonomy-model-law-example/)
- [Naic Taxonomy States Alabama Example](https://apis.io/examples/naic/naic-taxonomy-states-alabama-example/)

#### Collections (1)

Postman and Open Collection request collections.

- [NAIC Content JSON:API](https://apis.io/collections/naic/open-naic-content-jsonapi/)

#### Security (2)

Authentication, trust centre, and vulnerability disclosure.

- [Naic Authentication](https://apis.io/security/naic/naic-authentication/)
- [Naic Domain Security](https://apis.io/security/naic/naic-domain-security/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://content.naic.org/)
- [Documentation](https://content.naic.org/insurance-topics)
- [Support](https://content.naic.org/contact)
- [Blog](https://content.naic.org/newsroom)
- [Terms of service](https://content.naic.org/application/terms-conditions)
- [Privacy policy](https://content.naic.org/privacy_statement.htm)

## API Evangelist rating

**Kin Score 32.7** — thin · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 78.6 |
| Contract quality | 16.5 |
| Contract governance | 4.5 |
| Operational transparency | 0.0 |
| Developer ergonomics | 39.9 |
| Access clarity | 57.1 |

**Agent readiness 29.5** — agent-ready

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | na |
| MCP Server | — |
| Auth Clarity | bearer (partial credit) |
| Idempotency | na |
| Error Semantics | derived (partial credit) |
| OpenAPI Examples | partial |
| Rate Limit Signal | — |
| Event Surface Described | — |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | na |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | paginated |
| Operation Distinctiveness | distinct |

**Regulatory alignment 21.9** — Insurance

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/naic/](https://apis.io/providers/naic/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for NAIC: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/naic/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).

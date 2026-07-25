# NAIC (naic)

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

**Zero OpenAPI, Swagger, WSDL or AsyncAPI documents were found**, so this repo ships no `openapi/` directory.

The only API-shaped surface the NAIC names in public is **SERFF Web Services**, and it is partner-gated. Everything else — myNAIC, iSite+, SBS, OPTins, SERFF Login — is an Okta-fronted web application. Bulk regulatory data from the Financial Data Repository is licensed by contract (`idp@naic.org`) and delivered as CSV; InsData sells statutory financial statements as PDFs. Neither is an API.

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

## Related but distinct

**NIPR** (the National Insurance Producer Registry, [nipr.com](https://www.nipr.com)) is a separate legal entity from the NAIC even though the two share systems and branding. Any producer-licensing API activity belongs on the NIPR record, not this one.

## Maintainers

- Kin Lane — kin@apievangelist.com

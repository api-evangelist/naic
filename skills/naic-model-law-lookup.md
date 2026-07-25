---
name: Look up an NAIC model law
description: >-
  Find an NAIC model law, regulation or guideline by name or by its canonical MDL model number,
  and resolve its category and hierarchy, using the NAIC's public JSON:API. Use this when you
  need to cite a specific NAIC model (e.g. "MDL-668, the Insurance Data Security Model Law")
  rather than paraphrase it.
api: openapi/naic-content-jsonapi-openapi.yml
operations:
  - listTaxonomyTermModelLaws
  - getTaxonomyTermModelLaws
  - listTaxonomyTermModelLawCategories
  - getResourceIndex
generated: '2026-07-25'
method: generated
source: openapi/naic-content-jsonapi-openapi.yml (derived from https://content.naic.org/jsonapi)
---

# Look up an NAIC model law

The NAIC's model laws, regulations and guidelines are the organization's primary standards
output — the templates state legislatures and insurance departments adopt. There is no
documented API for them, but they are exposed as a taxonomy vocabulary on the NAIC's public
Drupal JSON:API, complete with their canonical MDL model numbers.

## Before you start

- **Base URL:** `https://content.naic.org/jsonapi`
- **Auth:** none. Every operation here is an anonymous `GET`. Do not send credentials.
- **Consumption terms:** the NAIC publishes `llms.txt` asking automated clients for a
  10-second crawl delay, a 100 request/day ceiling, and attribution as "NAIC" linking to
  `https://content.naic.org`. Honor it — there is no server-side rate limiting to stop you,
  which is exactly why you should throttle yourself. See `llms/naic-llms.txt`.
- **Content type:** requests and responses are `application/vnd.api+json`.

## Steps

### 1. Find the model law — `listTaxonomyTermModelLaws`

Filter by model number when you have it:

```
GET /jsonapi/taxonomy_term/model_laws
  ?filter[field_ml_model_number]=MDL-10
  &fields[taxonomy_term--model_laws]=name,field_ml_model_number,description,changed
```

Or search by name using the JSON:API condition form:

```
GET /jsonapi/taxonomy_term/model_laws
  ?filter[nm][condition][path]=name
  &filter[nm][condition][operator]=CONTAINS
  &filter[nm][condition][value]=Data Security
  &fields[taxonomy_term--model_laws]=name,field_ml_model_number
```

Always send `fields[...]`. Without it you get every attribute on every term.

The response is a JSON:API collection document: `data[]` of resource objects, each with a
UUID `id`, a `type` of `taxonomy_term--model_laws`, and your requested attributes.

### 2. Pull the full record — `getTaxonomyTermModelLaws`

Take the `id` from step 1 and resolve the category and hierarchy in one request:

```
GET /jsonapi/taxonomy_term/model_laws/{id}?include=field_ml_category,parent
```

The included resources land in the top-level `included` array. Note that `parent` may contain
the literal sentinel id `virtual` — that is Drupal's synthetic vocabulary root, not a real
term. **Stop walking the hierarchy when you hit it.**

### 3. Get the category vocabulary — `listTaxonomyTermModelLawCategories`

```
GET /jsonapi/taxonomy_term/model_law_categories?fields[taxonomy_term--model_law_categories]=name
```

Useful when you want to enumerate the corpus by subject area rather than by number.

## Paging

Offset pagination only, capped at 50 per page:

```
GET /jsonapi/taxonomy_term/model_laws?page[limit]=50&page[offset]=0
```

There is **no total count**. Follow `links.next` until it is absent; that is the end of the
collection.

## Errors you will actually hit

| Status | What it means | What to do |
|---|---|---|
| 400 | Your `filter`/`sort`/`fields` names a field that does not exist. Detail reads "Invalid nested filtering. The field `X` … does not exist." | Fetch one record with no `fields` param and read the real attribute names off it. |
| 404 (JSON) | The UUID does not resolve, or the term is unpublished. | Re-resolve the id from a collection query. Do not conclude the model law does not exist. |
| 404 (HTML) | You asked for a resource **type** that is not exposed — the request fell through to the site's HTML 404 page. | Check `content-type` before parsing. Enumerate valid types from `getResourceIndex`. |
| 405 | You used a write method. The detail lists the allowed ones. | This API is read-only for you. |
| 401 | You attempted a write. | The NAIC publishes no credentialing path. Do not retry. |

Full catalog: `errors/naic-problem-types.yml`.

## Cite it properly

Model laws are copyrighted NAIC material ("All content © 1991–2025 National Association of
Insurance Commissioners"). When you surface one, name the model number and the NAIC, and link
to `https://content.naic.org/model-laws`. Do not present the API record as the authoritative
text of the model — it is an index entry with a number, a name and a category, not the model
law document itself.

## What this will NOT get you

State adoption status, the full legislative text, or anything from SERFF, the Financial Data
Repository, SBS or OPTins. Those are gated systems, not on this API.

---
name: Pull the state insurance regulator directory
description: >-
  Retrieve NAIC's directory of state insurance department regulators — commissioners and staff,
  with position, term of office, elected/appointed provenance and public contact details —
  from the NAIC's public JSON:API, honoring the per-record privacy flags. Use this when you
  need to identify or contact the right regulator in a given state or NAIC zone.
api: openapi/naic-content-jsonapi-openapi.yml
operations:
  - listNodeStateDepartmentContact
  - getNodeStateDepartmentContact
  - listTaxonomyTermStateDepartments
  - listTaxonomyTermStates
  - listTaxonomyTermZones
generated: '2026-07-25'
method: generated
source: openapi/naic-content-jsonapi-openapi.yml (derived from https://content.naic.org/jsonapi)
---

# Pull the state insurance regulator directory

The United States has no federal insurance supervisor. Regulation is state-based, which means
"who regulates this" is always a fifty-plus-jurisdiction question. The NAIC maintains the
directory that answers it, and exposes it as `node--state_department_contact` on its public
JSON:API.

## Before you start

- **Base URL:** `https://content.naic.org/jsonapi`
- **Auth:** none — anonymous `GET` only.
- **Throttle yourself:** the NAIC's own `llms.txt` asks for `crawl_delay: 10` and
  `max_requests_per_day: 100`. Nothing enforces it server-side. Honor it anyway, and cache.
- **Privacy is on you.** See the mandatory step below.

## Steps

### 1. Get the department vocabulary — `listTaxonomyTermStateDepartments`

```
GET /jsonapi/taxonomy_term/state_departments
  ?fields[taxonomy_term--state_departments]=name
  &page[limit]=50
```

This gives you the department terms that contact records hang off. `listTaxonomyTermStates`
and `listTaxonomyTermZones` give you the state and NAIC-zone vocabularies if you want to group
by geography instead.

### 2. List the contacts — `listNodeStateDepartmentContact`

Ask only for the fields you need. The full record carries ~40 attributes.

```
GET /jsonapi/node/state_department_contact
  ?fields[node--state_department_contact]=title,field_contact_first_name,field_contact_last_name,field_naic_position_title,field_contact_title_position,field_term_of_office,field_elected,field_appointed,field_confirmed,field_leader,field_hide_email_from_public,field_hide_phone_from_public,field_contact_email_address,field_state_contact_phone,field_website
  &include=field_contact_state_department,field_state_department_category,field_zone
  &page[limit]=50
```

Filter to one department once you know its UUID:

```
GET /jsonapi/node/state_department_contact
  ?filter[field_contact_state_department.id]={department_uuid}
```

### 3. **Apply the privacy flags — do not skip this**

Every record carries two booleans:

- `field_hide_email_from_public`
- `field_hide_phone_from_public`

When either is true, the corresponding value **must be suppressed** in whatever you produce,
even though the payload may still contain it. These flags are the NAIC's stated publication
intent. Treating "it was in the JSON" as permission is the wrong read.

Also treat `field_regulator_biography` as editorial content about a named individual — quote
it, do not restate it as fact you inferred.

### 4. Resolve a single regulator — `getNodeStateDepartmentContact`

```
GET /jsonapi/node/state_department_contact/{id}?include=field_contact_state_department,field_zone
```

`field_related_regulator` points at another contact record when the NAIC has linked a
predecessor or a deputy — follow it only if you need the chain.

## Paging the whole directory

```
GET /jsonapi/node/state_department_contact?page[limit]=50&page[offset]=0
```

Follow `links.next` until it disappears. There is no total count. At 50 per page and a
10-second courtesy delay, a full directory sweep is a handful of requests — well inside the
NAIC's stated daily ceiling. Cache the result; this data changes on election and appointment
cycles, not daily.

## Freshness caveat

`feeds_feed--state_contacts` and `feeds_feed--state_contact_departments` exist on the resource
index, which tells you this directory is imported from an upstream system rather than authored
in place. Read `changed` on each record and say when the data was last updated rather than
implying it is live. Terms of office end; commissioners resign; a record that has not changed
in two years may be stale.

## Errors

Same set as every operation on this API — 400 on an unknown filter field, JSON 404 on an
unresolvable UUID, **HTML 404** if you misspell the resource type (check `content-type` before
parsing), 405 on a write method, 401 if you attempt a write. See
`errors/naic-problem-types.yml`.

## Attribution

Content is © the National Association of Insurance Commissioners. Attribute as "NAIC" and link
to `https://content.naic.org` per the publisher's `llms.txt`.

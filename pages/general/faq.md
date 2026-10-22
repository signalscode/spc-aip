# Frequently Asked Questions

## What is this repository?

Atonom's fork of Google's API Improvement Proposals. It is the **source of
truth** for public HTTP/OpenAPI API design. `bff-public-api` and related edge
contracts implement these AIPs.

## Which AIPs apply?

Only documents under `aip/general/`. Google Cloud, Firebase, Auth, AoG, and
client-library AIP areas were removed as out of scope.

## What if an AIP disagrees with bff-public-api?

Prefer the AIP. Update the BFF contract to comply, or propose an AIP amendment
if the guidance should change. The BFF is not the source of truth for design
rules.

## How do Atonom AIPs differ from google.aip.dev?

Where this fork diverges, the local AIP wins. Settled differences include opaque
string ids (format still open — see [TODO.md](../../TODO.md)), colon-delimited
custom methods (`:clone`, not a path segment), snake_case JSON,
`application/problem+json` errors (AIP-193), no public field masks / etags, and
PUT Replace for singletons with **final** Delete (no public restore).

Pagination (`skip`/`limit` vs cursors) and several other topics are **undecided**
and tracked in [TODO.md](../../TODO.md); do not treat draft AIPs as locked for
`/vN`.

## How do I run the site?

```bash
./serve.sh
```

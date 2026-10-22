# API Improvement Proposals (Atonom)

**TL;DR:** Design guidance for Atonom public HTTP/OpenAPI APIs, forked from
[Google AIPs](https://google.aip.dev/). This repo is the source of truth;
`bff-public-api` implements it.

## Overview

This repository is the **source of truth** for public API design. Edge contracts
in `bff-public-api` (and related BFFs) **must** follow the approved AIPs here.
It keeps Google AIP numbering and site tooling where useful, but drops Google
Cloud–, protobuf-, client-library-, and product-area-specific guidance that does
not apply to our JSON HTTP APIs.

## Scope

- **In:** resource-oriented HTTP design, standard and custom methods, fields,
  pagination, filtering, errors, naming, compatibility, and versioning for
  OpenAPI contracts under `bff-public-api/spec/api/endpoints/`.
- **Out:** protobuf packaging, gRPC transcoding, Google Cloud / Firebase /
  Actions on Google / client-library AIPs, long-running operations, batch RPCs,
  field masks, etags, and other patterns we do not expose publicly. Partial
  Update uses JSON Merge Patch (RFC 7396); see [AIP-134](aip/general/0134.md).

When a BFF contract disagrees with an approved AIP, **change the BFF** (or
propose an AIP amendment). Do not treat live OpenAPI as overriding this repo.

## Getting started

- Browse AIPs under [`aip/general/`](./aip/general/).
- FAQ: [`pages/general/faq.md`](./pages/general/faq.md)
- Contributing: [`CONTRIBUTING.md`](./CONTRIBUTING.md)

### Running the site locally

```bash
./serve.sh
```

## License

Except as otherwise noted, the content of this repository is licensed under the
[Creative Commons Attribution 4.0 License][1], and code samples are licensed
under the [Apache 2.0 License][2].

For the full text of each license, see [`LICENSE.md`](./LICENSE.md). Upstream
Google AIP content retains its original licensing; Atonom-specific edits are
under the same terms unless noted.

[1]: https://creativecommons.org/licenses/by/4.0/
[2]: https://www.apache.org/licenses/LICENSE-2.0

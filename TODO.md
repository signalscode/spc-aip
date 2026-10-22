# Open AIP decisions

Blocking gaps. Related AIPs are **`state: draft`** until these are resolved;
do not treat them as fully approved guidance for stable (`/vN`) contracts.

## Pagination model

**Status:** Undecided (AIP draft; blocking for stable `/vN` List)  
**AIP:** [AIP-158](aip/general/0158.md), [AIP-132](aip/general/0132.md)

List currently mandates offset pagination (`skip` / `limit` / `total`) and
forbids cursor tokens. Decide whether that stays, or whether stable List should
use (or also allow) cursor / page-token pagination.

Decide and document:

- Keep offset-only, switch to cursor-only, or support both (and which is default)
- Request/response field names (`skip`/`limit`/`total` vs `page_token` /
  `page_size` / `next_page_token`, or a different shape)
- Max page size, defaults, and invalid-value behavior
- Stability of offsets under concurrent inserts/deletes (document or reject)
- Whether changing the model later requires a new path prefix

Until resolved, treat AIP-158 as illustrative of today’s `/beta` shape, not a
forever ban on cursors for `/vN`.

Refs: `aip/general/0158.md`, `aip/general/0132.md` (List pagination).

## Idempotency for Create and custom POST

**Status:** Undecided (AIP draft; blocking for stable mutating POSTs)  
**AIP:** [AIP-133](aip/general/0133.md), [AIP-136](aip/general/0136.md)
(association PUT already requires idempotency in [AIP-124](aip/general/0124.md))

Only association Replace is required to be idempotent today. Create and
side-effecting custom methods (`POST …:clone`, etc.) have no retry / duplicate
guidance. Decide what clients may rely on.

Decide and document:

- Whether Create / custom POST must support an idempotency key (header or body)
- Key lifetime, scope (tenant / operation / resource), and replay response shape
- Behavior when the same key is reused with a different body
- Which methods are naturally idempotent without a key (if any)
- Interaction with `201` vs `200` on replay

Until resolved, do not assume retries of Create or custom POST are safe.

Refs: `aip/general/0133.md`, `aip/general/0136.md`, `aip/general/0124.md`.

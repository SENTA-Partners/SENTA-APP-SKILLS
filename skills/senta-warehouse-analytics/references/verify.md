# Verifying against the live warehouse

The ModMed dictionary in `modmed/` is vendor-supplied and stable. **Everything else in this
skill is empirical and decays.** Verify before betting a deliverable on a fact that is more
than a couple of months old, or whenever a number looks off.

## The Sigma MCP — the way to run a query

Tools: `begin_session` (**must be called first**), `search`, `list_documents`, `describe`,
`query`.

```
begin_session                                  → once per conversation
describe  { type: "table", inodeId: "<uuid>" } → CREATE TABLE DDL with real column names
query     { type: "connection", connectionId: "4ad9c97b-3c5d-4ada-821b-db8e4ce6381e",
            sql: "SELECT ... FROM \"connection\".\"<inodeId>\"" }
```

### Quirks that will cost you time

- **`query` type `connection` requires `"connection"."<inodeId>"` as the table reference.**
  Warehouse paths (`"MODMED"."DATA"."FIRM"`) fail with `Table ... not found`. Get inode ids
  from `search`.
- **Inode ids are not unique per table.** The same table is exposed through several
  connections, so a table has multiple inode ids (`PRIVATE.CORE.CAP` is both `e7537c86-…` and
  `8291f9dc-…`). Any one of them works; don't be surprised by the mismatch.
- **The SQL dialect is Sigma's, not Snowflake's.** `IFF()` fails — use `CASE WHEN`.
  `CURRENT_DATE()` with parens fails — use bare `CURRENT_DATE`. These do work:
  `DATEDIFF('day',a,b)`, `DATE_ADD('day',n,d)`, `DATE_TRUNC`, `MEDIAN`, `::DATE`, CTEs,
  window functions. No custom window frames, no ordered window aggregates, no t-quantile or
  incomplete beta (so no p-values in-warehouse).
- **`DATE_TRUNC('week')` truncates to Sunday here but Monday in Snowflake.** Weekly numbers
  will not match between the two. Pick one and say which.
- A query with no table reference errors `No connection found in sources` — always include a
  real `FROM`.
- Querying a data model or workbook element needs the **column ids** (`col-t-leak-5`), not
  display names. `describe` the element first.
- `query` type `workbook` runs against an element that **may carry hidden filters** which
  silently change the denominator. Check with `GET /v2/workbooks/{id}/queries` before
  trusting a rate.

## Enumerating the warehouse

The MCP `search` tool is fuzzy and will not list a schema's tables. `GET
/v2/connections/{id}/{databases|schemas|tables}` all **404**.

What works: **`GET /v2/files?typeFilters=table&limit=1000`, paginated via the `nextPage`
token** (a bare `page=N` integer silently re-serves the same page), then filter locally on
the returned `path` (`Connection Root/PRIVATE/CORE`). ~11.8K inodes, 12 pages.

Note `GET /v2/files` returns the folder id as **`id`**, not `inodeId`.

## Refreshing the ModMed reference files

**`MODMED.UTILITIES.MODMED_DATA_DICTIONARY` is the dictionary as a queryable table.** The
files in `references/modmed/` were generated from the V1.27.0 PDF/spreadsheet
(2025-06-23), but the warehouse copy is the live source — query it to regenerate or to check
whether a column exists before assuming the docs are stale.
`PUBLIC.MASTER.V_COLUMN_DESCRIPTIONS` is a second column-description source.

As of 2026-08-29 the dictionary is accurate: 415 documented names, 485 live in
`DATA` + `ANCILLARY`, only 1 documented table not live. The 71 undocumented live tables are
plumbing (`LINK_*` CDC watermarks, `*_LEGACY_BALANCE` conversion artifacts) plus
`CLAIM_SCRUB_RESULT`.

## Credentials

`SIGMA_BASE_URL` = `https://aws-api.sigmacomputing.com` (correct despite the org being "US
East"; regional hosts 400 on token exchange). Token: `POST {base}/v2/auth/token`, HTTP Basic
with base64 of `client_id:client_secret`, body `grant_type=client_credentials`, TTL ~1 hour.
Credentials are in `~/.claude/settings.json` (`env` block) and `~/.sigma-migration/env`.
**Never paste them into a session, a file, or a query.**

## Platform notes

- Windows PowerShell 5.1: `Invoke-WebRequest` needs `-UseBasicParsing`. A POST can succeed
  server-side even when the local call errors — check for orphaned objects.
- `jq` is not installed; use `python -c` for JSON. The compiled Sigma OpenAPI is 20MB and
  needs `open(..., encoding='utf-8')` or cp1252 blows up.

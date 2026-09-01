# Senta addendum

Everything else in this directory is the upstream **sigma-authoring** plugin by Thomas Wells
(MIT), version 1.12.2, vendored unmodified except that two directories were removed:

- `scripts/` — Ruby and shell tooling. The app's sandbox is Python-only with no network, so
  none of it can execute; shipping it would only mislead the model into trying.
- `generated/` — copies of the same guidance formatted for Cursor, Cline, Codex and Continue.

Keeping the upstream files untouched means a version bump is a clean replace. **Put local
findings here, not in the upstream files.**

## Verified against the Senta org, not covered upstream

**`POST /v2/workbooks/spec` returns no `url`.** The create response carries `workbookId` and
nothing clickable. The real link needs a follow-up `GET /v2/workbooks/{id}`, and it cannot be
constructed by hand: it carries an org slug and uses `workbookUrlId`, a short id that is *not*
the `workbookId`.

    POST → { "workbookId": "b25c7706-…" }                        // no url
    GET  → { "url": "https://app.sigmacomputing.com/senta/workbook/5qyTeeMVoev9HwLdlzXM3T" }

The app already does this follow-up. If you are told a workbook was created but no link
appeared, the workbook still exists — say so rather than implying the save failed.

## Senta conventions

**Workbooks the app creates are drafts in the user's own home folder**, pending data-team
review before publishing. Say that when reporting back, so nobody expects colleagues to see it
immediately.

**Connections in this org** (from `GET /v2/connections`) — all Snowflake:

| Connection | Id |
|---|---|
| Public | `683d83f7-7aee-4f28-a7ad-71e2bb6edfba` |
| Private | `c87cd700-7938-40df-8198-4bdf219ca0b1` |
| RCM_Connection | `90beb0c7-6597-4c1b-87e8-d3ae7b7abace` |
| SENTA_BI_1 | `a1688294-28e3-4870-8068-86732184748f` |
| Sys Admin | `4ad9c97b-3c5d-4ada-821b-db8e4ce6381e` |

Others exist (MKTG, SAGE, Sig_Admin, Sig_AI, BNSDEV, Sigma Audit Logs, Sigma Sample Database).
Route with `senta-warehouse-analytics` first — picking the right *source* matters more than
anything in this skill, and a beautiful workbook over the wrong table is worse than none.

## Confirmed-working minimal spec

Posted to the live API and read back intact — pages, all three elements, layout, and chart axes
all survived. A useful starting point when a larger spec is being rejected and you want to
bisect.

```jsonc
{
  "schemaVersion": 1, "kind": "workbook",
  "pages": [ { "id": "pg1", "name": "Overview" } ],
  "elements": [
    { "id": "hdr", "kind": "text", "body": "Charges by location." },
    { "id": "tbl1", "kind": "table",
      "source": { "kind": "sql", "connectionId": "683d83f7-7aee-4f28-a7ad-71e2bb6edfba",
                  "statement": "SELECT LOCATION_NAME AS LABEL, SUM(AMOUNT) AS N FROM … GROUP BY 1" },
      "columns": [ { "id": "c_label", "formula": "[Custom SQL/LABEL]" },
                   { "id": "c_n",     "formula": "[Custom SQL/N]" } ],
      "order": [ "c_label", "c_n" ], "visibleAsSource": true },
    { "id": "chart1", "kind": "bar-chart",
      "source": { "kind": "table", "elementId": "tbl1" },
      "columns": [ { "id": "x_label", "formula": "[Custom SQL/LABEL]" },
                   { "id": "y_n",     "formula": "Sum([Custom SQL/N])" } ],
      "xAxis": { "columnId": "x_label" }, "yAxis": { "columnIds": [ "y_n" ] } }
  ],
  "layout": "<?xml version=\"1.0\" encoding=\"utf-8\"?>\n<Page type=\"grid\" gridTemplateColumns=\"repeat(24, 1fr)\" gridTemplateRows=\"auto\" id=\"pg1\">\n  <Element elementId=\"hdr\" gridColumn=\"1 / 25\" gridRow=\"1 / 2\"/>\n  <Element elementId=\"tbl1\" gridColumn=\"1 / 13\" gridRow=\"2 / 8\"/>\n  <Element elementId=\"chart1\" gridColumn=\"13 / 25\" gridRow=\"2 / 8\"/>\n</Page>",
  "overlays": []
}
```

Two reminders that cost real time when learning this the hard way:

- **`csv-table` sources are workbook-scoped uploads.** Pointing at another workbook's CSV
  returns `CSV table does not belong to this workbook`. Use `sql` or `warehouse-table`.
- **`warehouse-table` column names are title-cased.** `SERVICE_DT` is `[Service Dt]`.

---
name: sigma-workbook-authoring
description: "Build a Sigma workbook from a spec — the JSON document shape, element kinds, column formulas, and the XML grid layout. Use whenever the user asks for a dashboard, a workbook, a chart someone else can open, or wants a result kept and shared rather than exported once. Covers what a valid spec looks like and the traps that make a spec silently produce an empty or wrong workbook."
---

# Authoring Sigma workbooks

`senta-warehouse-analytics` tells you **what to query**. This tells you **how to build something
someone can open**. Use both: route to the right source first, then shape the workbook.

Everything below was read from live workbooks in the Senta org, not from documentation.

## When to build a workbook rather than export a file

A workbook is right when the answer should stay live and be shared — a metric someone will
check again next month, a view a practice administrator should have permanently. An Excel
export is right for a one-off, or when the person needs to manipulate the numbers themselves.

Workbooks you create land as a **draft in the user's own folder** for the data team to review.
Say so when you report back, so nobody expects it to be live for colleagues immediately.

## The document shape

`POST /v2/workbooks/spec` takes `{name, folderId, document}`. The document is:

```jsonc
{
  "schemaVersion": 1,
  "kind": "workbook",
  "pages":    [ { "id": "pg1", "name": "Overview" } ],
  "elements": [ /* array — see below */ ],
  "layout":   "<?xml version=\"1.0\" encoding=\"utf-8\"?>\n<Page …>…</Page>",
  "overlays": []
}
```

Four things about this trip people up, and all four are silent failures:

1. **`elements` is an ARRAY, not a map.** Each element carries its own `id`.
2. **`layout` is an XML STRING, not an object.** An element that exists but is absent from the
   layout does not appear on the page. No error — just a blank dashboard.
3. **`pages` is an array of `{id, name}`.** The layout's `<Page id="…">` must match a page id.
4. **Writes are a full overwrite.** Updating a workbook replaces the whole document, so
   anything you did not include is removed. Never PATCH a partial document.

## Layout: a 24-column grid, expressed as XML

```xml
<?xml version="1.0" encoding="utf-8"?>
<Page type="grid" gridTemplateColumns="repeat(24, 1fr)" gridTemplateRows="auto" id="pg1">
  <Element elementId="kpi1"   gridColumn="1 / 9"  gridRow="1 / 3"/>
  <Element elementId="kpi2"   gridColumn="9 / 17" gridRow="1 / 3"/>
  <Element elementId="chart1" gridColumn="1 / 25" gridRow="3 / 9"/>
</Page>
```

`gridColumn` and `gridRow` are CSS grid line ranges — `"1 / 9"` means "start at line 1, end
before line 9", i.e. eight columns wide. Full width is `"1 / 25"`, not `"1 / 24"`. Rows are
roughly 40px; a KPI wants 2–3, a chart 5–8.

One `<Page>` per page, each in its own XML document string? No — the layout is a single string
containing every page's `<Page>` block in sequence.

## Elements

Every element has `id`, `kind`, and — except for text, dividers, buttons and containers — a
`source` and `columns`.

### Sources

```jsonc
"source": { "kind": "table", "elementId": "tbl1" }              // derive from another element
"source": { "kind": "csv-table", "connectionId": "…", "inodeId": "…" }  // base data
```

**Charts are almost always sourced from a table element, not from the connection directly.**
Build a `table` element that holds the query, then point the chart at it with `elementId`. That
is the pattern in every real workbook here, and it means the chart and the table cannot drift
apart.

### Columns and formulas

```jsonc
"columns": [
  { "id": "c_month",  "formula": "DateTrunc(\"month\", [Service Date])" },
  { "id": "c_charges","formula": "Sum([Charges])" },
  { "id": "c_prov",   "formula": "[AAA_AR_AGING/Provider]" }
]
```

- A **passthrough** column references the source: `[SourceName/Column Name]`.
- A **derived** column uses Sigma formula syntax: `Sum(…)`, `Count(…)`, `DateTrunc("month", …)`.
- `id` is yours to choose and is what charts point at. Keep them readable — `c_charges`, not a
  random string — because you will reference them from `xAxis` / `yAxis`.
- Sigma formula language is **not** Snowflake SQL. `DateTrunc("month", [x])`, not `DATE_TRUNC`.

**A `/` inside a column name breaks the reference.** If a source column is literally named
`A/R Balance`, a passthrough reference to it will not resolve — alias it in the underlying
dataset or query first.

### Charts point at column ids

```jsonc
{ "id": "chart1", "kind": "bar-chart",
  "source": { "kind": "table", "elementId": "tbl1" },
  "columns": [ /* as above */ ],
  "xAxis": { "columnId":  "c_month" },
  "yAxis": { "columnIds": ["c_charges"] },
  "stacking": "none" }
```

`xAxis.columnId` is singular; `yAxis.columnIds` is an array. Getting that backwards produces a
chart with no series and no error.

A chart re-declares every column it uses, including passthroughs it inherits from the source
table. That is why real chart elements carry long column lists — it is expected, not redundant.

### Element kinds, by frequency in this org

`control` · `table` · `pivot-table` · `button` · `container` · `text` · `kpi-chart` ·
`bar-chart` · `line-chart` · `divider` · `combo-chart` · `input-table` · `donut-chart` ·
`pie-chart`

Per-kind keys are in `references/element-catalogue.md`. Read it before using a kind you have
not built before — guessing a key name fails silently rather than erroring.

## Building one that works

1. **Route the source first** using `senta-warehouse-analytics`. A beautiful workbook over the
   wrong table is worse than no workbook.
2. **One `table` element holding the query**, with every column you need.
3. **Charts and KPIs sourced from that table** by `elementId`.
4. **Write the layout XML**, placing every element. Anything omitted is invisible.
5. **Keep the first version small** — a KPI row and one chart. A spec that fails is hard to
   debug because Sigma reports little; a small spec that works is easy to extend.

## Traps

- **`Accept: application/json`** on spec endpoints, or you get YAML back. Omitting it during a
  create has been observed to leave an orphaned duplicate workbook.
- **Text elements use `body`, not `text`.** (Buttons do use `text`.)
- **Colour schemes apply in alphabetical order of category value**, not the order you list
  series. If a specific category must be a specific colour, set it explicitly.
- **Not every existing workbook round-trips.** Some older ones fail to re-import their own
  exported spec. Do not assume "GET the spec, change one thing, POST it back" is safe on an
  established workbook — build new rather than rewriting something people depend on.
- **`visibility: "hidden"`** on a page keeps working data out of the way; several production
  workbooks here use a hidden `Data` page.

## Reporting back

Give the workbook name and URL, say it is a draft in their own folder pending data-team review,
and describe in one line what it shows. Do not paste the spec.

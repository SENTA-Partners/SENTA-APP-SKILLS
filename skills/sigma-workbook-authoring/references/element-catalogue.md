# Element catalogue

Derived from 8 production workbooks in the Senta Sigma org
(1833 elements). Not from documentation — this is what
the API actually returns, so it is what it will accept.

**"Always present"** means the key appeared on every instance of that kind, so treat it as
required. **"Also seen"** is optional. A key absent from both lists is one this org has never
used; verify against a real workbook before relying on it, because an unrecognised key is
ignored silently rather than rejected.

## `control`  ·  553 seen

- **Always present:** `controlId`, `controlType`, `id`, `kind`
- **Also seen:** `actions`, `clearLabel`, `date`, `endDate`, `filters`, `includeNulls`, `includeToday`, `max`, `min`, `mode`, `name`, `selectionMode`, `showClearLabel`, `source`, `startDate`, `style`, `unit`, `value`, `values`

## `table`  ·  353 seen

- **Always present:** `columns`, `id`, `kind`, `order`, `source`, `visibleAsSource`
- **Also seen:** `actions`, `conditionalFormats`, `description`, `filters`, `groupings`, `name`, `noDataText`, `sort`, `style`, `tableStyle`

## `pivot-table`  ·  252 seen

- **Always present:** `columns`, `id`, `kind`, `source`, `values`
- **Also seen:** `actions`, `axisTotals`, `columnsBy`, `conditionalFormats`, `description`, `display`, `filters`, `frozenColumn`, `name`, `rowsBy`, `style`, `tableStyle`, `totals`

## `button`  ·  143 seen

- **Always present:** `appearance`, `fillColor`, `id`, `kind`, `text`
- **Also seen:** `actions`, `align`, `borderRadius`, `fontColor`, `fontWeight`, `size`

## `container`  ·  129 seen

- **Always present:** `id`, `kind`
- **Also seen:** `elementGap`, `style`

## `text`  ·  98 seen

- **Always present:** `body`, `id`, `kind`
- **Also seen:** `verticalAlign`

## `kpi-chart`  ·  87 seen

- **Always present:** `columns`, `id`, `kind`, `source`, `value`
- **Also seen:** `actions`, `comparison`, `comparisonColumn`, `description`, `filters`, `layout`, `name`, `periodComparison`, `style`, `timeline`, `trend`

## `bar-chart`  ·  70 seen

- **Always present:** `columns`, `id`, `kind`, `source`, `xAxis`, `yAxis`
- **Also seen:** `color`, `dataLabel`, `description`, `filters`, `gap`, `legend`, `name`, `orientation`, `stacking`, `style`, `tooltip`

## `line-chart`  ·  53 seen

- **Always present:** `columns`, `id`, `kind`, `source`, `xAxis`, `yAxis`
- **Also seen:** `color`, `dataLabel`, `description`, `filters`, `legend`, `lineAreaStyle`, `name`, `refMarks`, `style`

## `divider`  ·  47 seen

- **Always present:** `id`, `kind`
- **Also seen:** `align`, `direction`, `style`

## `combo-chart`  ·  20 seen

- **Always present:** `columns`, `id`, `kind`, `name`, `source`, `xAxis`, `yAxis`
- **Also seen:** `color`, `conditionalFormats`, `dataLabel`, `description`, `filters`, `gap`, `legend`, `pointStyle`, `seriesLineAreaStyle`, `stacking`, `style`, `tooltip`

## `input-table`  ·  16 seen

- **Always present:** `columns`, `id`, `inputMode`, `kind`, `name`, `source`
- **Also seen:** `filters`, `sort`

## `donut-chart`  ·  8 seen

- **Always present:** `color`, `columns`, `hole`, `id`, `kind`, `legend`, `name`, `source`, `value`
- **Also seen:** `dataLabel`, `description`, `filters`, `holeValue`, `style`, `trellis`

## `pie-chart`  ·  2 seen

- **Always present:** `color`, `columns`, `dataLabel`, `id`, `kind`, `name`, `source`, `value`

## `chat`  ·  1 seen

- **Always present:** `agentId`, `id`, `kind`

## `image`  ·  1 seen

- **Always present:** `id`, `kind`, `source`


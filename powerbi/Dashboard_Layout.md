# Dashboard blueprint — Alpha service profitability

**Page:** 16:9 canvas, 1280 × 720 layout. Suggested theme: navy title band, teal section headers, white / light-gray backgrounds, and restrained conditional formatting.

## Wireframe

```text
┌────────────────────────────────────────────────────────────────────────────┐
│ ALPHA | Service Profitability Comparison        [Reporting month slicer]    │
├────────────────────────────────────────────────────────────────────────────┤
│  TOTAL REVENUE       TOTAL COST          PROFIT             PROFIT MARGIN   │
│  2,850 Mn Toman      2,080 Mn Toman      770 Mn Toman       27.0%           │
├────────────────────────────────────────────┬───────────────────────────────┤
│ Revenue vs Total Cost vs Profit             │ Profit Margin by Service     │
│ Clustered column chart by ServiceName       │ Horizontal bar / data label  │
├────────────────────────────────────────────┼───────────────────────────────┤
│ Service economics table                    │ Key insights                  │
│ Service | Revenue | Cost | Profit | Margin  │ Cloud profit +30 Mn Toman    │
│ Colo    | 1,850   | 1,480| 370    | 20.0%   │ Cloud margin +20 pp          │
│ Cloud   | 1,000   | 600  | 400    | 40.0%   │ Cloud profit share 51.9%     │
└────────────────────────────────────────────┴───────────────────────────────┘
```

## Visual specifications

1. **KPI cards:** Total Revenue, Total Cost, Profit, Profit Margin. Use the DAX measures in `Measures.dax`.
2. **Clustered column chart:** Axis = `DimService[ServiceName]`; Values = Total Revenue, Total Cost, Profit. Use million Toman labels and no truncated axis for the margin visual.
3. **Profit margin by service:** Bar chart with `DimService[ServiceName]` as category and `Profit Margin %` as value; data labels in percent.
4. **Economics table:** Revenue, non-labor direct cost, labor cost, total cost, profit, margin, billable units, profit per billable unit.
5. **Key insight text:** Make the higher Cloud margin visible but pair it with a caveat that full capacity utilization is assumed.
6. **Slicer:** `DimDate[Month Start]` if a date table is built; otherwise `Monthly_Fact[PeriodStart]`. With the supplied sample data there is only one month to select.

## Build steps

1. Import `data/Monthly_Fact.csv` and `data/DimService.csv`.
2. Set data types as described in `Data_Model.md` and create the relationship on `ServiceKey`.
3. Create the DAX measures in `Measures.dax`; optionally create and mark `DimDate` as a date table.
4. Add visuals in the order above and format monetary values as `#,##0;(#,##0);-` with titles indicating Mn Toman.
5. Validate the report against `excel/alpha_service_profitability.xlsx` before publishing.

**Scope note:** This repository provides the source dataset, DAX, model, dashboard specification and Excel workbook specification. A native `.pbix` file is not generated here; the blueprint is intended for implementation in Power BI Desktop.

# Excel workbook specification

The distributable bundle contains alpha_service_profitability.xlsx. This specification documents the workbook structure in source control.

## Sheets

- **Inputs** — editable operating assumptions in million Toman, with blue-font inputs and source/assumption notes.
- **Monthly_Fact** — Power BI-ready fact table with one row per service-month; formula-derived billable units, revenue, cost, profit and margin.
- **Service_Summary** — monthly comparison, combined totals, revenue share and clustered-column chart.
- **Data_Dictionary** — field-level definitions and import types.

## Core formulas

For each service:

- Billable units = Asset count × units per asset × utilization.
- Revenue = billable units × unit price.
- Infrastructure / direct cost = asset count × infrastructure cost per asset.
- Labor cost = asset count × labor cost per asset.
- Total cost = infrastructure/direct cost + labor cost.
- Profit = revenue − total cost.
- Profit margin = profit ÷ revenue.
- Revenue share = service revenue ÷ combined revenue.

## Expected checks (million Toman per month)

| Service | Revenue | Infrastructure | Labor | Total cost | Profit | Margin |
|---|---:|---:|---:|---:|---:|---:|
| Colocation | 1,850 | 1,120 | 360 | 1,480 | 370 | 20.0% |
| Cloud | 1,000 | 500 | 100 | 600 | 400 | 40.0% |
| Combined | 2,850 | 1,620 | 460 | 2,080 | 770 | 27.0% |

The date 2026-10-01 is only an illustrative month because the input did not specify a reporting month.

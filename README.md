# Alpha — Service Profitability Analysis

پروژه نمونه‌کار تحلیل سودآوری ماهانه دو خدمت **Colocation** و **Cloud** بر اساس ورودی‌های تمرین. داده‌ها، معیارهای DAX، مدل داده، طرح داشبورد و گزارش فارسی در همین ریپازیتوری قرار دارند.

## Key results (monthly, million Toman)

| Metric | Colocation | Cloud | Combined |
|---|---:|---:|---:|
| Revenue | 1,850 | 1,000 | 2,850 |
| Infrastructure / direct cost | 1,120 | 500 | 1,620 |
| Labor cost | 360 | 100 | 460 |
| Total cost | 1,480 | 600 | 2,080 |
| Profit | 370 | 400 | 770 |
| Profit margin | 20.0% | 40.0% | 27.0% |

Cloud returns **30 million Toman more monthly profit** with lower revenue, and its margin is 20 percentage points higher.

## Repository structure

- `data/Monthly_Fact.csv` — Power BI-ready fact table, one row per service-month.
- `data/DimService.csv` — service dimension and assumptions.
- `powerbi/Measures.dax` — DAX measures for revenue, cost, profit, margins, and unit economics.
- `powerbi/Data_Model.md` — model relationships, data types, grain and ER diagram.
- `powerbi/Dashboard_Layout.md` — dashboard wireframe, visual requirements and implementation steps.
- `reports/executive_summary_fa.md` — Persian executive report.
- The complete downloadable project bundle includes the formula-driven Excel workbook and one-page Word report.

## Power BI quick start

1. Import `data/Monthly_Fact.csv` and `data/DimService.csv` using **Get Data → Text/CSV**.
2. Create the 1:* single-direction relationship `DimService[ServiceKey]` → `Monthly_Fact[ServiceKey]`.
3. Add measures from `powerbi/Measures.dax`.
4. Follow `powerbi/Dashboard_Layout.md` to build KPI cards, a revenue/cost/profit comparison, margin bars, and an economics table.

## Assumptions and limitations

- All 10 Colocation racks are assumed billed; all 200 Cloud VMs are assumed sold as specified in the task.
- Financial amounts are monthly and in million Toman.
- `PeriodStart=2026-10-01` is a sample date for modeling because a real reporting month was not supplied. It must not be treated as a real transaction date.
- Taxes, depreciation, capex, financing costs and unspecified overheads are excluded.
- Only one illustrative month is provided, so this supports a comparative snapshot, not a time-trend analysis.
- A native Power BI `.pbix` file is not generated; the repository contains the data, DAX, model and dashboard blueprint for building it in Power BI Desktop.

Source: assumptions supplied in the task; no external data used.


## GPU Ready Rack — Market Opportunity Assessment

A Persian market-opportunity assessment for a GPU Ready Rack service has been added under [`gpu-ready-rack/`](gpu-ready-rack/). It includes the market analysis, exhibition playbook, target-account shortlist with weighted scoring, scenario-based revenue model, source register, and sample DAX measures. Figures for prices, rack counts, and win rates are assumptions for sensitivity analysis, not confirmed customer quotes or a validated forecast.

- [Project README](gpu-ready-rack/README.md)
- [Market report](gpu-ready-rack/reports/market_analysis_fa.md)
- [Exhibition strategy](gpu-ready-rack/reports/exhibition_strategy_fa.md)
- [Target-account shortlist CSV](gpu-ready-rack/data/target_account_shortlist.csv)
- [Source register](gpu-ready-rack/data/sources.csv)

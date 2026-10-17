# Data files

- `Monthly_Fact.csv`: Power BI fact table, one row per service-month. Financial values are in **million Toman**. `PeriodStart = 2026-10-01` is a placeholder reporting month; it is not a claim that the provided data belongs to a real October 2026 transaction period.
- `DimService.csv`: one row per service, intended to serve as a small service dimension and input reference.

The task states that all Cloud VM capacity is sold. For Colocation, the model assumes all 10 listed racks are billed at the stated price. Input values come from the user-provided task; no external sources were used.

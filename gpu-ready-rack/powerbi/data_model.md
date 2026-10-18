# Power BI data model — GPU Ready Rack

- **Targets**: one row per target account, key `ID`; scores, priority, direct pipeline, racks, win probability and source.
- **Revenue_Model**: one row per Low/Base/High scenario; monthly price, term, nominal ARR and scenario-weighted ARR.
- **Exhibition_Plan**: segment, target accounts, primary message, CTA and KPI.
- **Sources**: one row per evidence item; date checked and limitations.
- **Customer_Canvas**: discovery/qualification fields and next actions.

## Relationship guidance
Relate `Customer_Canvas[AccountID]` (*:1) to `Targets[ID]` where the canvas has one row per account. If retaining multiple meetings per account, normalize with a separate Account dimension and activity fact. Keep the three revenue scenarios disconnected from Targets unless a scenario dimension is introduced.

## Dashboard guidance
KPI cards: target accounts, P1 accounts, direct pipeline, expected base ARR. Add sorted bar chart for account score, priority/opportunity matrix, low/base/high ARR comparison, and qualification gaps/next-action table. Use slicers on Priority, OpportunityType and Stage.

All prices, racks and win probabilities are assumptions, not confirmed quotes or historical conversion rates. Validate physical GPU need and buying process before forecasting.

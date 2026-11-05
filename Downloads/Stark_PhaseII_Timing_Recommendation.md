# Stark Phase II: timing recommendation and readiness status

Recommendation: compare every chart series on SUPPLIER SHIP DATES. The orange series measures remaining to be shipped, so using supplier dispatch dates throughout gives a consistent timing comparison without inventing delivery receipts.

| Series | Date used in the aligned demonstration | Quantity meaning |
|---|---|---|
| Blue initial plan | Initial on-dock promise O minus calendar transit days | Starting quantity less original planned lots due to ship |
| Purple revised plan | Revised on-dock promise T minus transit; valid unrevised lots retain O minus transit | Future remaining balance under the valid recovery forecast; includes quantities due to ship today |
| Orange actual | Actual supplier ship dates R and W, unchanged | Starting quantity less valid actual shipments through AS OF |
| Red deadline | Earliest buyer expedited on-dock need I for the part, minus transit | Required ship-by date |

Example: an on-dock promise of November 10 with five calendar days of transit means a planned ship date of November 5. An actual November 5 shipment is on time. Transit is subtracted once from plan/need dates and is not added to orange actual ship dates.

The existing detail table continues to show estimated on-dock dates (actual dispatch plus transit). Entered promise dates, need dates, shipment dates, quantities, IDs and notes have not been changed by this alignment. TODAY(), validation, protection, formatting, chart layout and the four-tab structure are preserved. Chart legends and explanatory text identify the ship-date basis. The workbook's existing calendar-day transit convention is retained.

## Requested tasks

| Task | Status |
|---|---|
| Replace fictional data with verified business data | BLOCKED: no approved business-data source was supplied. Available attachments and the repository workbook identify fictional SIM data. No production records were invented. |
| Align chart timing | COMPLETED in Stark_PhaseII_Aligned_Ship_Dates_DEMO.xlsx. All four series now use ship dates. |
| Native Microsoft Excel recalculation | NOT PERFORMED: no Microsoft Excel application or connected Excel document session is available in this environment. |

## Validation performed

LibreOfficeDev 26.8.0.0.alpha0 was used for full recalculation and rendered-chart inspection. All 14 aligned demonstration charts were visually reviewed. Independent raw-record calculations passed six cases and 19,320 chart checks, with no unexpected formula errors. The demonstration's ending remaining quantity is 815.

Cases: aligned demonstration; an on-time shipment; an initial shipment one day behind its plan; a revised quantity due to ship on AS OF; zero transit days; and a required ship-by date before the cycle start. The on-time case's blue/orange quantities coincide. The late case shows 70 remaining against an initial-plan target of zero on the missed ship date. The due-today revision is included rather than silently skipped. Purple remains absent for parts without revisions.

The delivered Excel file is assembled from the prior workbook's OOXML with targeted chart/helper changes and freshly calculated values. It is not the LibreOffice-rewritten workbook. Existing style, protection and validation definitions were preserved, including the x14 validation extension.

## Needed before live use

1. Supply the approved current open-order export and the supplier's initial/revised plans and actual shipment log, including the PO-line/schedule keys and verified transit days. The existing simulation start/date entries remain test data until those approved records are supplied.
2. Open the populated candidate in native Microsoft Excel; record the Excel version, ensure Automatic calculation, run a full recalculation, save, close and reopen it. Confirm TODAY() and the approved reconciliation totals, inspect all charts and retain legitimate risk warnings. An Excel-saved copy plus the application/version and observed results is needed for review. This is a requested test, not a claim that it has been performed here.

LIVE STATUS: NOT APPROVED. The timing demonstration is available for review; verified-data replacement and native Excel validation remain outstanding.

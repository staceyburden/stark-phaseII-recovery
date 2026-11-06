# Transit review and three-day chart ticks

This demonstration preserves the current meaning of O/T: entered promised ON-DOCK (arrival) dates. No order, planned quantity, promise date, actual shipment quantity/date, need date or note was changed.

## Date rule

Promised on-dock date = promised supplier ship date + the supplier-selected calendar transit days.

- If O/T contain arrival dates, transit is already included in those entries and must not be added again.
- Actual estimated arrivals are calculated as R + selected transit and W + selected transit, exactly once.
- The ship-date charts derive planned ship dates as O/T minus transit and the required ship-by date as buyer on-dock need minus transit. Orange uses actual R/W ship dates and remaining-to-ship quantities.
- Remaining-lot forecast checks account for transit when deciding whether a future on-dock promise is achievable from AS OF. Legitimate plan/date warnings are retained.

O/T are currently input cells, not automatic arrival-date formulas. If the supplier is actually entering planned SHIP dates there, that requires a different entry/calculation design; it must be confirmed before those entries are reinterpreted. The current workbook has not silently converted or extended supplier commitments.

Example: five calendar days of transit and a promised November 10 arrival imply a planned November 5 shipment. An actual November 5 shipment estimates arrival November 10, not November 15.

## Corrections made

1. Every chart has bottom major tick marks and date labels at three-day intervals. Data and curve calculations were not resampled.
2. The supplier's transit entry O9 on tab 2 is now editable and validated for whole calendar days from 0 to 365. Previously it was locked and linked to a tab 1 setting.
3. There is one transit source: tab 2 O9. Tab 1 B224 is a protected synchronized mirror; the TransitDays name points to O9. The existing selected value of five days is retained.
4. Revised-plan status and the chart horizon now guard invalid/missing transit settings and show warnings instead of producing hidden #VALUE! errors.

## Audit and tests

Inventoried and checked 64,553 formulas across all four tabs, including hidden rows/columns and chart helpers. Found no broken/external references, circular value dependencies or unexpected cached formula errors in the default case. The review identified 12,374 transit-dependent formulas.

Zero-, five- and ten-day transit cases passed 9,660 independent chart checks across blue, orange, purple and red. Estimated arrivals were separately checked against raw actual shipment dates plus the selected days. Invalid-text and blank-transit cases correctly produce explicit warnings without formula errors. The demonstration still ends with 815 remaining to be shipped.

All 14 charts were rendered and inspected with LibreOfficeDev 26.8.0.0.alpha0. Three-day ticks are retained. All entered data, existing validation extensions, four-tab layout and other protection remain. Only the transit field/mirror protection styles were changed as required for supplier entry. Native Microsoft Excel validation has not been performed.

Latest refresh: recalculated November 6, 2026. TODAY() evaluates to November 6 in this checked copy. The whole-workbook formula audit and zero-/five-/ten-day chart checks were rerun successfully. Quantity inputs and all entered order/promise/shipment dates remain unchanged. Date-related plan-update warnings may change as AS OF advances.

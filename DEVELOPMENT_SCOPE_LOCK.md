# EAS Finance Workspace — Development Scope Lock

This file is the regression baseline for the Development module. A later UI or refactor must not remove a capability below without an explicit product decision.

## Product principle

Development is the principal EAS differentiator. The product should combine a very fast borrower/developer front end with lender-quality monthly finance mechanics and diagnostic insight. Quick and Detailed are two input depths over the same underlying development-finance logic, not separate calculators.

## Quick Development Test

- One project must work perfectly on its own.
- Developer may add up to three more projects, maximum four.
- Projects may be ground-up or conversion/refurbishment.
- Duplicate/remove project.
- Project-specific acquisition/current site value, existing debt where owned, works, professional/other costs, contingency, GDV, works period, exit period, units and developer cash.
- Common editable finance assumptions across projects.
- Default quick finance assumptions: 12.0% p.a. interest, 2.0% arrangement fee, 0% exit fee, rolled interest, 100% works funding test, one-month certification/reimbursement lag.
- Works and exit periods must materially affect finance cost.
- Generated monthly S-curve for quick-mode works unless a more suitable type-specific profile applies.
- Month-by-month acquisition, cost draws, interest, debt reduction and exit receipts.
- Show economics before finance and after estimated finance.
- Show estimated interest/finance cost, peak debt, peak debt/GDV, peak debt/project cost, developer equity, additional liquidity/equity required, exit shortfall and indicative equity return/IRR where meaningful.
- Market-position message must consider both leverage and structure. It must not be a fundable/not-fundable verdict.
- Comparison should identify separate leaders (profit, margin, capital efficiency, leverage, time, market breadth), not invent one opaque EAS score.
- Quick scenarios should include at least build cost +10%, GDV -10%, build delay, sales delay and combined downside.
- Any quick project can be promoted into Detailed without re-keying the main figures.

## Detailed Development Model

### Position and economics
- Site being purchased or already owned.
- Historic land cost, current value/economic contribution and current cash requirement remain separate.
- Acquisition costs, core works, professional fees, statutory/infrastructure, abnormals, contingency, finance, disposal and discrete event costs can remain distinct.
- Ground-up and conversion/refurbishment have contextual risk questions and different quick defaults where justified.

### Monthly cash flow and timing
- Monthly cash-flow engine is authoritative where timing data exists.
- Generated schedule is available when no detailed data is supplied.
- Native Excel/CSV import should map existing spreadsheets into the internal schema.
- Imported/generated monthly rows must drive drawdowns, peak debt, interest and liquidity; they are not display-only.
- Actual periods are immutable in scenario reforecasting; scenarios alter forecast periods only.
- Actual versus forecast state must remain visible.

### Funding
- Senior and optional mezzanine.
- Committed/facility amount, drawn/undrawn position and peak utilisation/headroom.
- Eligible-use funding logic, not merely one total LTV/LTC percentage.
- Acquisition, works and professional-fee funding percentages/eligibility.
- 100% works funding can be tested where relevant.
- Certification/reimbursement lag / arrears funding.
- Rolled and serviced interest.
- Rates and lender fees.
- Senior repayment priority before mezzanine unless explicitly modelled otherwise.
- Release mechanism on unit sales.
- Explicit developer equity injections where cash/draw timing leaves a liquidity gap.

### Costs and shocks
- Professional fees and separate project cost categories.
- Contingency reserve and consumption.
- Timed jump/abnormal events.
- Option for jump event to consume contingency first or sit outside contingency.

### Exit
- Phased unit sales.
- Release percentages/minimum release amounts.
- Sales/disposal costs.
- Part-sell/part-retain.
- Retained-unit refinance.
- Development exit-finance comparison.
- Fee-inclusive break-even horizon for switching to exit finance.
- Closing development debt/exit shortfall clearly shown.

### Outputs
- Economic project cost before finance.
- Profit before finance.
- Total interest and total finance cost.
- Profit after finance and profit on total cost after finance.
- Peak senior/mezz/total debt.
- Peak debt/GDV and peak debt/project cost.
- Developer equity represented/required.
- Additional equity/liquidity requirement and peak single-month injection.
- Facility headroom.
- Developer equity IRR where meaningful.
- Monthly funding ledger.
- Scenario table and diagnostic alerts.

### Scenario controls
At minimum:
- Construction duration.
- Sales duration.
- Build cost.
- Completed value/GDV.
- Unexpected cost event.
- Combined downside.

### Excel / data transport
- Standard Excel/CSV template.
- Existing spreadsheet import with column mapping/synonyms and user confirmation.
- Canonical fields should support Period, Status, Category, Subcategory, Description, Forecast, Actual and Source.
- Export Detailed model to Excel with inputs, monthly ledger, scenarios and imported cost plan.
- Project/model manifest with schema/version.
- Calculation engine remains authoritative; Excel is data transport/interoperability, not the calculation authority.

## Borrower UX

- Borrower language on screen; technical underwriting language underneath.
- Quick should not require a borrower fact-find before testing project economics.
- Detailed may ask borrower/cash/security position before deeper financing.
- One fact entered once.
- Ownership/equity, willingness to provide security and actual security/charge remain distinct.
- Wider asset equity is context, not automatically cash.
- Persistent `Discuss with the experts` route to EAS.
- Case export must include the important outputs visible on screen.

## Market interpretation

- Core mathematics is separate from dated lender-policy/reference overlays.
- No universal lender fundability verdict.
- Broad market / narrower market / specialist structure language is acceptable when clearly indicative.
- Ground-up and conversion/refurbishment may use different broad leverage references.
- Lender criteria and pricing must eventually live in a dated governed reference layer rather than permanent UI constants.

## Scope exclusions / boundaries

- EAS does not arrange regulated mortgages. The workspace must not route regulated residential owner-occupier borrowing as an EAS product.
- No tax engine.
- No planning prediction engine.
- No formal valuation engine.
- No claim that current lender criteria/pricing are live unless a dated live-data layer is actually connected.
- Monthly development convention may be used in the generic engine; lender-specific daily interest/day-count belongs in lender-specific overlays.

## Required regression gates

Before a Development build is promoted:

1. Run the original/core golden-case logic or equivalent regression cases.
2. Verify Quick and Detailed use consistent finance mechanics.
3. Verify works/sales timing changes finance cost and peak debt.
4. Verify owned-site equity is not treated as cash.
5. Verify actual history is unchanged by scenario reforecasting.
6. Verify senior/mezz repayment and facility headroom.
7. Verify contingency/jump-cost behaviour.
8. Verify sale releases, retain/refinance and exit shortfall.
9. Verify Excel/CSV mapping and export paths.
10. Verify one-project and four-project Quick journeys.
11. Verify transfer from Quick to Detailed without re-keying.
12. Verify case export and persistent EAS handoff.
13. Run browser/mobile/accessibility/security smoke tests.
14. Record any deliberate exclusions explicitly rather than silently dropping them.

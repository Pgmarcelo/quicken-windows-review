# Export intake

## Recommended first review package

Collect the smallest package needed; a useful default is the last 12 complete months plus current month-to-date, with snapshots at a common date. A partial package can still support a partial review.

| Evidence | Purpose | Important fields |
|---|---|---|
| Detailed transactions or QIF | Spending, cash flow, recurring charges | Account, date, payee, category, split, amount, transfer destination, currency |
| Income/expense or spending report | Reconciliation and category trends | Period, account/category filters, subtotals, currency |
| Account balances / net-worth report | Assets and liabilities | As-of date, ownership, balance, currency, excluded accounts |
| Holdings / portfolio report | Allocation and exposure | Account, security/ticker, quantity, price/date, market value, cost basis where available, currency |
| Investment performance report | Return cross-check | Date range, account/security scope, return method, flows |
| Debt statements or supplied terms | Payoff projections | Balance/date, APR, minimum, compounding, renewal/maturity, prepayment restrictions |
| Budget and scheduled obligations, if available | Forward cash planning | Budget vs actual, due dates, irregular costs, planned contributions |

Ask for missing data only when relevant. Mortgage principal and interest may require statements. Investment fees, fund holdings, pension details, tax room, and RSU vesting terms may need provider documents. Exported Quicken cost basis is not automatically a verified tax cost basis under the applicable jurisdiction's rules.

## Windows export route

Official source, checked November 3, 2026: [Quicken Windows: Exporting data](https://info.quicken.com/win/export-data-from-quicken).

- Reports: Reports > Reports & Graphs Center; select and show the report, then Export > Export to Excel Worksheet. Export applies to reports, not graphs. Labels and available reports vary by release/edition; verify the actual UI rather than inventing exact report names.
- QIF: File > File Export > QIF file; choose destination, account, dates, and relevant export contents. Include account/category/security lists where needed. Verify account coverage from the resulting file rather than assuming all accounts were exported.
- Clipboard report export can provide tabular text if worksheet export is unavailable. PDFs are a fallback; verify extracted tables and totals visually.
- QDF and QDF-backup are not analysis exports. Do not treat them as SQLite, rename them to CSV, or reverse-engineer the live file. QXF, QFX/OFX, and QIF are distinct formats; do not assume a parser for one handles another. Quicken's documentation includes import instructions for migration; this review stops after export.

## Parsing and traceability

Inspect actual structure before selecting a parser. Reports can contain title rows, repeated headers, subtotal/grand-total rows, blank separators, formatted negatives, and mixed currencies. Do not sum both detail and subtotals. Preserve account context when unpivoting grouped reports.

QIF can contain multiple record types/accounts, split detail, transfers, opening balances, security actions, prices, and locale-dependent dates. Preserve record identifiers and unknown action codes. Handle transaction parents and splits as alternatives for aggregation, not additive records. Investment actions require action-specific semantics; an ordinary cash-transaction parser is insufficient. If parsing coverage is incomplete, create report exports for affected sections; ask the user only when access is blocked.

Do not automatically delete candidate duplicates: legitimate identical purchases exist. Prefer stable IDs if present; otherwise flag matching account/date/amount/payee/split fingerprints and investigate export overlap. Record exclusions and reasons. A transaction date is not proof of settlement, vesting, or valuation date.

# Open Quicken, export, and review

An invocation to run the review authorizes opening the installed Quicken app, navigating reports, choosing temporary report filters, and saving new local exports in the current authorized workspace. It does not authorize changing financial records, downloading bank transactions, syncing, trading, or importing files. Do not require the user to prepare exports.

Use the available computer-use skill and follow its current app-selection, observation, input, and recovery instructions. Discover the app/window each session rather than storing window IDs or screen coordinates. Use the current Quicken file. If several candidate files/windows exist, resolve from context or ask which one. For a locked desktop, authentication, or file password, ask the user to handle that step; do not automate authentication.

Default review: last 12 complete months, current month-to-date separately, and balances/holdings as of today in the active client's time zone. Announce these assumptions and continue without a setup questionnaire. Ask goal/risk/tax questions only when needed for decisions, not to block collection or descriptive analysis.

Create a dated run folder in outputs for exports and final findings; keep intermediate parsing work in work. Use fresh descriptive filenames to avoid overwrites. Record the open file title, report name, filters, period, currency, and export timestamp in a manifest. Avoid saving changes over the user's saved report definitions.

Collect available evidence in this order, adapting to the actual edition:

1. Net Worth and/or Account Balances snapshot, in the reporting currency, with account coverage recorded. Identify separate/excluded accounts, unvested compensation, and nonzero hidden accounts without changing their settings.
2. Detailed banking/transaction export or QIF covering all relevant accounts and categories, including split/transfer information. Supplement with income/expense by month for reconciliation. Use actual report controls to confirm dates rather than relying on remembered defaults.
3. Investment holdings/portfolio value by account and security; prices and currencies; investment performance for the same period if available.
4. Loan/mortgage information and upcoming bills/income sufficient for cash planning. Read terms available in Quicken; request only genuinely missing APR, renewal, payment, or provider information after supported analysis.

Quicken's observed Windows export menu can offer Excel Workbook, tab-delimited Text, and PDF. Text is suitable for machine-readable reports and avoids launching Excel. QIF is an alternative, not a requirement when detailed report exports suffice. Never import an export back into Quicken. Never use email/share controls to export.

After each export, confirm the completion UI and verify the actual file exists, is nonempty, has expected headers/date range/currency, and contains the full report rather than only the visible screen. Do not claim an export succeeded based only on clicking Save. Preserve source bytes. Reconcile the resulting data using analysis.md, and continue through the analysis and prioritized recommendations in SKILL.md in the same task.

If an export path fails, inspect the current UI and retry once using a supported alternate format or report. If still blocked, record the exact missing section, continue other available sections, and explain the concrete blocker. Do not repeatedly restart, invent missing numbers, or shift the entire export task to the user. Leave Quicken open and dismiss temporary export dialogs when finished.

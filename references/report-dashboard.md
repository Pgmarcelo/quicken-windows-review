# Standard financial review and dashboard

Read this for every full review. The user's default is a written review plus an HTML dashboard, not an export-only or chat-only answer. For a narrow follow-up, update only affected outputs when requested. An explicit user request for a different format takes precedence.

## Reproduce the result, refresh the evidence

Use current exports for a new review. If the user asks to reproduce/restyle a previous review, use that review's verified calculations and clearly retain its original as-of date. Do not silently present an old snapshot as current. Dates, balances, categories, rates, warnings, and recommendations are data, not fixed template text. Do not store actual personal financial figures or raw exports in the skill.

Create a dated folder under the authorized outputs location, preserving previous runs. Include:

| File | Content |
|---|---|
| financial-review-YYYY-MM-DD.txt | Full written analysis, scorecard, findings, assumptions, source locations, prioritized next steps |
| financial-dashboard-YYYY-MM-DD.html | Self-contained interactive dashboard, with all charts and essential values already present before scripts run |
| dashboard-preview-YYYY-MM-DD.html | Script-free version with the same findings, drawn charts, exact details and fixed example savings figures |
| review-calculations-YYYY-MM-DD.json | Exact numeric values, units, periods, confidence limits, calculated scenarios and reconciliation results |
| review-manifest-YYYY-MM-DD.json | Input filenames/hashes, export scope, account/date/currency coverage, observed loan terms, exclusions and verification status |
| financial-review-YYYY-MM-DD.zip | Both dashboards, written review, calculation/manifest files and linked report exports |

Keep raw QIF local and link it only when useful; it need not be included in the dashboard download. Copy supporting exports with their relative filenames so package links work. If an app locks an export during packaging, read it without modifying it and stage an identical byte copy in work; verify the copy's hash, then package the staged files. Do not terminate Quicken to release a lock.

## Dashboard design and content

Use the established calm design: cream page, dark green heading area, white rounded panels, restrained green/amber charts and readable text. Responsive layout: four summary cards across on desktop, two on small screens; stack paired panels on narrow screens. Provide navigation to Overview, Spending, Debt & cash, Investments, Next steps, Money words. Include a print/save-PDF control in the interactive version and print styles. Keep charts directly labelled and accessible without depending on colour.

Use this order, adapting when evidence is missing:

1. **Your money, made clear:** snapshot date, reporting currency and tax jurisdiction when known, exact spending period, and notice that figures are rounded.
2. **Financial picture:** recorded net worth, investment value, mortgage/debt balance and accessible-bank-cash starting point. Explain each number; never label unverified available cash as spendable. Show exact amounts in expandable details.
3. **Main finding:** the most consequential supported takeaway. A reported category surplus must be distinguished from cash after loan principal, capital purchases, savings contributions and transfers.
4. **What you own and owe:** show assets, debts and net worth with proportional bars; describe home concentration when supported. State which property values are estimates.
5. **Spending:** larger nonoverlapping categories with exact detail, major one-offs, a clearly labelled partial or complete cash reconciliation, and monthly category differences. Exclude partial months from complete-month charts and annual averages; show month-to-date separately. Use “money listed as coming in” for gross category inflows, with an immediate explanation that this is not take-home pay.
6. **Debt and safety cushion:** recorded payment, balance/rate, estimated home equity, early-payment checks, card data gaps and accessibility of reserves. Separate bank cash, investment-account cash, foreign assets, restricted accounts and unvested compensation.
7. **Investments:** recorded value, security-type breakdown, concentration and material data-quality issues. Quicken classifications are not fund look-through allocation. Explain placeholders and missing purchase costs beside the figures; withhold unsupported return/tax-gain claims.
8. **Next steps:** prioritized actions with evidence, a practical next step, and estimated benefit or “not yet known.” Do not populate a fixed number of recommendations with filler.
9. **Savings calculator:** choose supported, nonoverlapping spending groups and clearly labelled percentage-reduction scenarios. Choose groups from current evidence and user goals, or show that no scenario is supported. Display annual and average monthly savings, assumptions, and exact amounts. Baseline × reduction percentage is the calculation; actual savings are not guaranteed. Keep scenario controls separate from actual Quicken records.
10. **Money words:** short definitions for terms actually used. Examples: net worth = what you own minus what you owe; principal = loan amount paid back; interest = lender's charge; liquidity = how quickly you can access money; cost basis = recorded purchase cost used in working out a gain. Explain applicable tax cost-basis adjustments when relevant. Define RSUs/vesting and tax-advantaged accounts if used.
11. **Reliability and sources:** distinguish arithmetic checks passed from real-world facts still unverified. Include missing inputs, source report links, current authoritative guidance supporting consequential recommendations, and next review checkpoint.

## Language and numbers

The reader prefers simple words. Lead with what a figure means for their choices. Explain a technical term at its first use, not only in the glossary. Avoid jargon such as “reconciliation,” “allocation,” “liability,” or “FX” without a plain explanation. Keep short paragraphs and visible next steps.

Round headline figures for scanning; retain exact amounts at the currency's supported precision in details, table cells, accessible chart descriptions or hover labels. State the reporting currency clearly. Distinguish recorded values, estimates, missing values and proposed scenarios. Never turn missing information into zero. Never present a partial cash bridge's remainder as a spending allowance. Do not double-count dining cuts within a broader food cut, or count a debt payment as both spending and a transfer.

## HTML and delivery checks

- Build a standalone HTML document with inline styles, data and code; no external libraries, fonts, tracking, uploads or network data requests. Financial information stays local. No need to publish or host the dashboard.
- Render all essential figures, charts and tables into the HTML before adding optional interactivity. If JavaScript is unavailable, the report must remain useful. The preview copy has no script tags or live controls; show the fixed example assumptions/results instead.
- Scope interactive code to an IIFE or module to avoid global-variable collisions in preview hosts. Keep JSON data valid and safely embedded. Use explicit element IDs. Do not assume host-specific APIs, local storage or network access.
- Check syntax, data parsing, required elements, input handlers and math using an available local runtime. Verify the calculator at default, zero and boundary values; verify monthly charts contain only complete months and that printed units/dates match the review. Check static chart/table content exists in the preview file and that it contains no scripts or unfilled placeholders.
- Inspect desktop/mobile rendering in a permitted preview when available. If preview access is blocked, do not bypass its security restriction or claim visual validation. State the limitation briefly. A static fallback is not proof that the chat renderer works.
- Confirm ZIP entries, nonempty files and working relative source paths. Keep dynamic and preview figures consistent with the written review and JSON. Preserve original export hashes.
- Final reply: link the preview/dashboard and download package, identify the period/as-of date, and mention only the most material limitation. For a chat-preview error, offer the script-free copy and the package that the user can extract and open in their own browser; do not insist the preview is repaired without evidence.

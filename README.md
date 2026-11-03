# Quicken Windows Financial Review

A reusable agent skill for Quicken Classic for Windows. It opens Quicken, creates local exports, reviews household finances, and produces a clear written report and HTML dashboard.

## What it covers

- Spending, cash flow, recurring costs and improvement opportunities.
- Debt balances, repayment scenarios and cash reserves.
- Investments, concentration, missing cost records and valuation limits.
- Net worth, foreign currencies and contingent compensation.
- Plain-language recommendations, rounded headlines and exact details.

Every full review includes an interactive dashboard, a script-free preview, calculation data, an evidence manifest and a downloadable report package. Canada and CAD are defaults; other jurisdictions and currencies can be requested.

## Install

Copy this repository's contents into your agent's `quicken-windows-review` skill folder. For Codex, use `~/.codex/skills/quicken-windows-review/` or a workspace's `.agents/skills/quicken-windows-review/`.

Invoke with `$quicken-windows-review` and ask for a full review. Desktop export requires a compatible Windows computer-use tool and an unlocked Quicken session. Existing exports are also supported.

## Scope and privacy

The workflow creates exports and analyzes them. It does not edit the QDF database, import transactions, trade, move money or cancel services. It does not require bank credentials or a new financial-data service. Financial records and generated reports remain local unless the user explicitly authorizes another destination.

This repository contains reusable instructions only, with no real financial exports, account data or personal report examples. Analysis remains dependent on data quality and does not replace provider statements or verified tax records.

## Files

- `SKILL.md`: entry point and workflow.
- `agents/openai.yaml`: display metadata.
- `references/desktop-export.md`: desktop export workflow.
- `references/exports.md`: supported exports and intake.
- `references/analysis.md`: calculations and accounting rules.
- `references/report-dashboard.md`: report/dashboard format and validation.

Not affiliated with or endorsed by Quicken.

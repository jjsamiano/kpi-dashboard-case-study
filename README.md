# KPI Dashboard Case Study

A single static page (`index.html`, no build step, no dependencies) that
presents the output of the [`02-python-etl-reconciliation`](../02-python-etl-reconciliation)
pipeline the way I'd present it in a weekly data quality review — the same
job a Power BI or Tableau dashboard does, built here as plain HTML/CSS/JS so
it's viewable with just a browser, no BI license required.

**Note on data:** every number on the page comes from the synthetic sample
dataset in the companion SQL and Python projects. No employer or client
data is used.

## What it shows

- **KPI tiles** — unique contacts, duplicates resolved, cross-system match
  rate, discrepancies flagged
- **Field completeness** meters and a **match breakdown** bar (matched /
  CRM-only / marketing-only)
- **Discrepancy log** — the field-level conflicts flagged for manual review
  instead of being auto-merged
- **Pipeline view** — the three-stage flow (SQL dedup → Python fuzzy dedup →
  cross-system reconciliation) with record counts at each stage

## View it

Open `index.html` directly in a browser, or serve the folder with GitHub
Pages for a live link (see the setup steps in the top-level portfolio
README).

## Why static HTML instead of a Power BI/Tableau export

Power BI and Tableau workbooks need a viewer license or a paid publish
tier to share a live link — not something a portfolio should depend on.
Rebuilding the same KPI view as a static page keeps it viewable by anyone,
for free, while still reflecting the actual dashboard design decisions
(what to surface as a headline number vs. supporting detail, how to flag
exceptions without hiding them) from my Power BI/Tableau work at Security
One2One and Roami.

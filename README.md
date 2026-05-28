# Power BI — Executive Revenue Dashboard

> A single-page executive report tracking revenue performance, growth, margin, and budget variance across regions, products, segments, and channels. Built on a star-schema semantic model with advanced DAX, drill-through, and a forecasting page.

![Power BI](https://img.shields.io/badge/Power%20BI-Executive%20Report-yellow)
![DAX](https://img.shields.io/badge/DAX-Time%20Intelligence%20%7C%20Forecast-green)
![Model](https://img.shields.io/badge/Model-Star%20Schema-blue)

---

## What's in here

| File | Purpose |
|------|---------|
| [`dashboard-mockup.html`](dashboard-mockup.html) | **Live interactive mock** of the report layout (open in a browser). Stands in for the `.pbix` screenshot — same visuals, real synthetic data. |
| [`dax/measures.dax`](dax/measures.dax) | Full DAX measure library: revenue, time intelligence, margin, budget variance, forecasting |
| [`data/revenue_data.csv`](data/revenue_data.csv) | Synthetic source data (720 rows, FY2023–FY2025) |
| [`generate_data.py`](generate_data.py) | Reproducible data generator |
| [`docs/report-design.md`](docs/report-design.md) | Page-by-page report design, drill-through, bookmarks, UX |
| [`docs/data-model.md`](docs/data-model.md) | Star-schema model and relationships |

> The interactive HTML is included because GitHub renders a screenshot the same as any reviewer would see — but here a reviewer can actually click through the charts. In the real Power BI Service this is a Direct Lake report off the certified semantic model from Project 1.

## Report pages

1. **Executive Summary** — 5 KPI cards (Revenue, YoY, Gross Margin, Budget Variance, Top Product), revenue-vs-budget trend with 3-month moving average, region donut, product drill-through table, margin trend, segment/channel breakdown.
2. **Product Detail** (drill-through target) — selecting a product line opens region/segment/channel mix and monthly trend for that product.
3. **Forecast** — next-6-month revenue forecast using a DAX linear-trend model with confidence band.

## Key features demonstrated

- **Revenue KPIs** — total, YoY, MoM, QoQ, rolling 12-month.
- **Trend analysis** — actual vs budget, moving averages, margin-over-time.
- **DAX measures** — time intelligence, variance, RANKX segmentation, dynamic switching.
- **Drill-through** — product line → product detail page.
- **Forecasting** — linear-regression DAX forecast with upper/lower band.
- **Executive reporting** — clean single-screen layout, certified-dataset badge, daily refresh cadence.

## How to view

Open `dashboard-mockup.html` in any browser — no build step, charts render from embedded data.

## Results framing

The layout follows executive-reporting best practice: top-line KPIs first, one primary trend visual, then supporting breakdowns — readable in under 10 seconds, with drill-through for analysts who need detail.

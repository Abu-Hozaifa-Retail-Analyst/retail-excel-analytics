# Retail Excel Analytics

A portfolio of Excel-based retail analytics projects — each one solves a real
store-operations problem (sales reporting, inventory, promotions, forecasting)
using progressively more advanced Excel skills, from `SUMIFS` through
Power Query and DAX.

Built as a learning-by-doing project: every workbook uses live formulas
(no hardcoded numbers), so changing an input recalculates the whole model.

**Status: all 6 projects complete.**

## Skills demonstrated across this repo

| Skill area | Where it shows up |
|---|---|
| Data cleaning, `TEXT`, `TRIM`/`CLEAN`, data validation | Raw data prep in every project |
| `VLOOKUP`/`XLOOKUP`, `INDEX`/`MATCH` | 02, 03 |
| `SUMIFS`/`COUNTIFS`/`AVERAGEIFS` | 01, 02, 03 |
| PivotTables & PivotCharts | 01, 03 |
| Conditional formatting, data bars | 01, 02 |
| Power Query | 03, 06 |
| Power Pivot / Data Model | 06 |
| DAX basics (`SUMX`, `CALCULATE`) | 06 |
| Forecasting (`FORECAST.ETS`, trendlines) | 04 |
| What-If Analysis, Goal Seek, Data Tables | 05 |
| Dashboard design (slicers, timelines, form controls) | 01, 05 |
| Macros/VBA basics | 06 |

## Projects

| # | Project | Business Problem | Status |
|---|---|---|---|
| [01](./01-sales-dashboard) | Retail Sales Performance Dashboard | A regional manager needs a one-page view of sales, profit, and margin by store, category, and month. | ✅ Complete |
| [02](./02-inventory-abc-analysis) | Inventory ABC Analysis & Reorder Point Model | Warehouse is overstocked on low-value SKUs and stocking out on high-value ones. | ✅ Complete |
| [03](./03-market-basket-analysis) | Customer Basket & Market Basket Analysis | Identify which products are frequently bought together to guide store layout and promos. | ✅ Complete |
| [04](./04-demand-forecasting) | Demand Forecasting for Reordering | Predict next month's demand per SKU to avoid stockouts and overstock. | ✅ Complete |
| [05](./05-markdown-simulator) | Markdown & Promotion Impact Simulator | Model the margin impact of a 10/20/30% category discount before running it. | ✅ Complete |
| [06](./06-multistore-consolidation) | Multi-Store Sales Consolidation Pipeline | 10+ stores send separate weekly CSV exports — combine and standardize automatically. | ✅ Complete |

Each project folder has its own `README.md` with the specific problem statement,
techniques used, and key insights.

## Results at a glance

| Project | Headline finding |
|---|---|
| 01 Sales Dashboard | Downtown leads all stores by revenue; Footwear is the top category |
| 02 ABC Analysis | 8 of 20 SKUs (40%) drive ~78.5% of inventory value — a clean 80/20 split |
| 03 Market Basket | Hoodie + Chinos is the strongest pair (Lift ≈ 5.1); Earbuds + Charging Cable is the most common strong pair (14% of baskets) |
| 04 Demand Forecasting | `FORECAST.ETS` cut forecast error more than half vs. a naive average (9.2% MAPE vs. 20.4%) |
| 05 Markdown Simulator | 3 of 5 categories have a *negative* break-even discount — any markdown loses money for them under current elasticity assumptions |
| 06 Multi-Store Consolidation | Caught 47 duplicate rows (3.8% of raw data) automatically; standardized 18 store-label variants down to 6 |

## Repo structure

```
retail-excel-analytics/
├── README.md                       ← you are here
├── 01-sales-dashboard/
│   ├── sales_dashboard.xlsx
│   └── README.md
├── 02-inventory-abc-analysis/
│   ├── inventory_abc_analysis.xlsx
│   └── README.md
├── 03-market-basket-analysis/
│   ├── market_basket_analysis.xlsx
│   └── README.md
├── 04-demand-forecasting/
│   ├── demand_forecasting.xlsx
│   └── README.md
├── 05-markdown-simulator/
│   ├── markdown_promotion_simulator.xlsx
│   └── README.md
├── 06-multistore-consolidation/
│   ├── multistore_consolidation.xlsx
│   └── README.md
└── datasets/
    └── README.md
```

## How this repo was built

Each project follows the same loop:

1. Learn the Excel skill through a real retail problem (see the mentor prompt below).
2. Practice on a small realistic (often synthetic) dataset.
3. Build the full workbook as a portfolio-ready deliverable.
4. Document the problem, technique, and findings in that folder's `README.md`.

<details>
<summary>Mentor prompt used to learn each skill</summary>

```
Act as a senior retail analytics mentor teaching me advanced Excel through
real business problems. I am a [beginner/intermediate/advanced] Excel user
learning retail analytics to build a portfolio for GitHub.

For each topic, do the following:
1. Explain the retail business problem it solves in 2-3 sentences.
2. Teach the specific Excel feature/function needed.
3. Give me a small realistic retail dataset to practice on.
4. Give me 3 practice tasks of increasing difficulty using that dataset.
5. Give me the "answer key" logic so I can check my formulas.
6. Suggest how this exercise could become a GitHub portfolio project.

Topic to teach me today: [INSERT TOPIC]
```

</details>

## License

Code and workbook structure are MIT licensed (see [`LICENSE`](./LICENSE) —
swap in your name before publishing). Datasets in this repo are synthetic,
generated for practice purposes — not real POS data from any company.

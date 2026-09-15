# Retail Excel Analytics

A portfolio of Excel-based retail analytics projects focused on practical
business problems in sales, inventory, customers, promotions, forecasting,
and multi-store operations.

The projects are built using live Excel formulas and progressively advanced
analytical techniques.

**Status: 6 core projects complete; Project 02 is currently being upgraded.**

## Skills Demonstrated

| Skill | Projects |
|---|---|
| Data cleaning and validation | Across projects |
| SUMIFS / COUNTIFS / AVERAGEIFS | 01, 02, 03 |
| VLOOKUP / XLOOKUP / INDEX-MATCH | 02, 03 |
| SUMPRODUCT and ranking logic | 02 |
| ABC inventory classification | 02 |
| XYZ demand variability analysis | 02 |
| Coefficient of Variation (CV) | 02 |
| Centralized model assumptions | 02 |
| PivotTables / PivotCharts | 01, 03 |
| Conditional formatting | 01, 02 |
| Power Query | 03, 06 |
| Power Pivot / Data Model | 06 |
| DAX | 06 |
| Forecasting | 04 |
| What-If Analysis / Goal Seek | 05 |
| Dashboard design | 01, 05 |
| VBA basics | 06 |

## Projects

| # | Project | Business Problem | Status |
|---|---|---|---|
| 01 | [Retail Sales Performance Dashboard](./01-sales-dashboard) | Monitor sales, profit, margin, stores, categories, and monthly performance. | Complete |
| 02 | [Retail Inventory Optimization & Replenishment Analytics](./02-inventory-abc-analysis) | Identify high-value and variable-demand SKUs and support better inventory decisions. | Upgrade in progress |
| 03 | [Customer Basket & Market Basket Analysis](./03-market-basket-analysis) | Identify products frequently purchased together to support layout and promotions. | Complete |
| 04 | [Demand Forecasting for Reordering](./04-demand-forecasting) | Forecast future SKU demand to reduce stockout and overstock risk. | Complete |
| 05 | [Markdown & Promotion Impact Simulator](./05-markdown-simulator) | Evaluate discount and margin impact before running promotions. | Complete |
| 06 | [Multi-Store Sales Consolidation Pipeline](./06-multistore-consolidation) | Combine and standardize sales files from multiple stores. | Complete |

## Results at a Glance

| Project | Key Finding |
|---|---|
| 01 Sales Dashboard | Downtown leads stores by revenue; Footwear is the top category. |
| 02 Inventory Optimization | 8 of 20 SKUs are Class A and account for 78.50% of annual usage value. |
| 03 Market Basket | Hoodie + Chinos is the strongest product pair by lift. |
| 04 Demand Forecasting | Forecasting reduced error compared with a naive average approach. |
| 05 Markdown Simulator | Several categories become unprofitable under markdown scenarios. |
| 06 Multi-Store Consolidation | Duplicate rows and inconsistent store labels were identified and standardized. |

## Project 02 Upgrade

Project 02 is being upgraded from a basic ABC and reorder-point model into a
broader inventory optimization and replenishment solution.

Current analytical flow:

```text
SKU Data
   ↓
Centralized Assumptions
   ↓
ABC Analysis
   +
XYZ Analysis
   ↓
Reorder Point
   ↓
Safety Stock
   ↓
EOQ
```

### Completed Project 02 Capabilities
ABC classification based on annual usage value
Dynamic ABC thresholds
ABC summary and validation
Centralized service-level assumptions
Centralized Z-score assumptions
XYZ classification based on demand variability
Coefficient of Variation (CV)
Dynamic XYZ thresholds
XYZ summary and validation
Safety-stock calculations
Reorder-point calculations
EOQ calculations

### Current Project 02 Results

ABC classification:

Class	SKU Count	Annual Usage Value	Value Share
A	8	$217,451.00	78.50%
B	6	$43,744.00	15.79%
C	6	$15,802.00	5.70%
Total	20	$276,997.00	100.00%

### XYZ classification:

Class	SKU Count
X	16
Y	4
Z	0
Total	20

The current dataset contains no Z-class SKUs because no SKU has a CV above
the current Z threshold.

## Repository Structure


```
retail-excel-analytics/
│
├── README.md
│
├── 01-sales-dashboard/
│   ├── sales_dashboard.xlsx
│   └── README.md
│
├── 02-inventory-abc-analysis/
│   ├── inventory_optimization.xlsx
│   └── README.md
│
├── 03-market-basket-analysis/
│   ├── market_basket_analysis.xlsx
│   └── README.md
│
├── 04-demand-forecasting/
│   ├── demand_forecasting.xlsx
│   └── README.md
│
├── 05-markdown-simulator/
│   ├── markdown_promotion_simulator.xlsx
│   └── README.md
│
└── 06-multistore-consolidation/
    ├── multistore_consolidation.xlsx
    └── README.md


## Project Method

Each project follows a practical analytics workflow:

Define the retail business problem.
Prepare and validate the data.
Build the Excel analytical model.
Validate formulas and business logic.
Translate results into business insights.
Document the project.
Commit meaningful milestones to Git.

Mentor prompt used to learn each skill
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

### Data & portfolio note

The datasets used in these projects are synthetic and generated for learning
and portfolio purposes. They do not represent real POS, supplier, customer,
or company data.

The analytical models are designed to demonstrate retail problem-solving,
Excel modeling, validation, and business decision-support skills.

## License

Code and workbook structure are MIT licensed (see [`LICENSE`](./LICENSE) —
swap in your name before publishing). Datasets in this repo are synthetic,
generated for practice purposes — not real POS data from any company.

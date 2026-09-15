# 02 · Retail Inventory Optimization & Replenishment Analytics

**Business problem:** The warehouse needs different inventory policies for different SKUs. Managing every SKU with the same review cadence, safety-stock rule, and replenishment approach can lead to excess inventory on low-value items and stockout risk on important or unpredictable items. This model combines inventory value, demand variability, lead time, and replenishment metrics to support more targeted inventory decisions.

## File

[`inventory_optimization.xlsx`](./inventory_optimization.xlsx)

## Objective

Build an Excel-based inventory analytics model that helps a retailer:

- Identify the SKUs that contribute most to inventory value
- Classify products by demand predictability
- Apply differentiated inventory-control logic
- Calculate safety stock and reorder points
- Calculate Economic Order Quantity (EOQ)
- Create a foundation for more advanced inventory optimization and replenishment decisions

## Key analytical capabilities

### ABC Analysis

Classifies SKUs according to their contribution to annual inventory usage value.

- **Class A:** Highest-value SKUs requiring the tightest control
- **Class B:** Medium-value SKUs requiring balanced control
- **Class C:** Lower-value SKUs suitable for leaner control

### XYZ Analysis

Classifies SKUs according to demand variability using the Coefficient of Variation (CV).

- **Class X:** Relatively stable and predictable demand
- **Class Y:** Moderately variable demand
- **Class Z:** Highly unpredictable demand

Combining ABC and XYZ analysis provides a stronger foundation for inventory policy because it considers both **financial importance** and **demand predictability**.

## Excel techniques used

- `SUMPRODUCT` for a sort-free cumulative-value running total
- `RANK` to order SKUs by annual usage value without physically re-sorting the table
- Nested `IF` classification into A/B/C tiers
- `COUNTIF` and `SUMIF` for ABC and XYZ summary analysis
- `INDEX` and `MATCH` for retrieving classification and service-level parameters
- `IFERROR` for controlled handling of calculation errors
- Coefficient of Variation (CV) to measure demand variability
- XYZ classification based on configurable CV thresholds
- Centralized assumptions for ABC, XYZ, service-level, and Z-score parameters
- Differentiated safety-stock calculations by inventory class
- Reorder point and EOQ calculations
- Conditional formatting for inventory classification and decision support
- Dashboard KPI calculations and Pareto-style visualization

## Sheet guide

| Sheet | Purpose |
|---|---|
| `Dashboard` | Executive inventory KPIs and decision-support visuals |
| `SKU Data` | 20-SKU input table and inventory-related assumptions |
| `Assumptions` | Centralized ABC, XYZ, service-level, and Z-score parameters |
| `ABC Analysis` | Annual usage value, ranking, cumulative value share, and A/B/C classification |
| `XYZ Analysis` | Demand variability using CV and X/Y/Z classification |
| `Reorder Point Model` | Safety stock, reorder point, EOQ, and annual ordering metrics |

## Methodology

### Annual Usage Value

**Annual Usage Value = Unit Cost × Annual Units Sold**

This metric estimates the annual inventory value associated with each SKU and is used as the basis for ABC classification.

### ABC Analysis

SKUs are ranked by annual usage value and their cumulative share of total annual usage value is calculated without manually sorting the source table.

The current classification thresholds are:

- **Class A:** cumulative value share ≤ 80%
- **Class B:** cumulative value share > 80% and ≤ 95%
- **Class C:** cumulative value share > 95%

The thresholds are centralized on the `Assumptions` sheet so they can be changed without modifying the analytical formulas.

### Current ABC results

Based on the current synthetic dataset:

| Class | SKU Count | Annual Usage Value | Value Share |
|---|---:|---:|---:|
| A | 8 | $217,451.00 | 78.50% |
| B | 6 | $43,744.00 | 15.79% |
| C | 6 | $15,802.00 | 5.70% |
| **Total** | **20** | **$276,997.00** | **100.00%** |

The ABC summary is dynamically calculated from the underlying SKU data.

### XYZ Analysis

XYZ analysis measures demand predictability using the **Coefficient of Variation (CV)**.

**CV = Demand Std Dev ÷ Avg Daily Demand**

The current model uses the following configurable thresholds:

- **Class X:** CV ≤ 50%
- **Class Y:** CV > 50% and ≤ 100%
- **Class Z:** CV > 100%

These thresholds are model assumptions and can be adjusted on the `Assumptions` sheet.

### Current XYZ results

Based on the current synthetic dataset:

| Class | SKU Count |
|---|---:|
| X | 16 |
| Y | 4 |
| Z | 0 |
| **Total** | **20** |

The XYZ classification is dynamically linked to the centralized assumptions rather than hardcoded into the SKU rows.

### Safety Stock

Safety stock is calculated using the service-level Z-score, demand variability, and lead time.

**Safety Stock = Z × Demand Std Dev × √Lead Time**

Higher-priority inventory classes can therefore receive higher service-level targets and greater protection against demand variability.

### Reorder Point

**Reorder Point = Avg Daily Demand × Lead Time + Safety Stock**

This estimates the inventory level at which a replenishment order should be triggered.

### Economic Order Quantity

**EOQ = √(2 × Annual Demand × Order Cost ÷ Holding Cost)**

EOQ estimates an order quantity intended to balance ordering and inventory holding costs.

## Current business insights

The current synthetic dataset shows:

- **8 of 20 SKUs (40%) are Class A**, accounting for **78.50% of annual usage value**.
- **6 of 20 SKUs are Class B**, accounting for **15.79% of annual usage value**.
- **6 of 20 SKUs are Class C**, accounting for only **5.70% of annual usage value**.
- The ABC distribution demonstrates that a relatively small number of SKUs account for most inventory usage value.
- XYZ analysis currently classifies **16 SKUs as X**, **4 as Y**, and **0 as Z**.
- The combination of ABC and XYZ provides a more useful inventory-management framework than ABC classification alone because it considers both value contribution and demand predictability.

## Data note

`SKU Data` is a synthetic dataset generated for portfolio analysis.

Unit costs and prices are shared with `01-sales-dashboard` for portfolio continuity. Annual demand, demand variability, lead time, order cost, and holding cost are illustrative assumptions and do not represent real supplier or retailer data.

The workbook is designed so that changing the underlying inputs and centralized assumptions automatically flows through the downstream analytical calculations.

## Validation

The workbook includes validation checks to confirm that:

- ABC class counts reconcile to the total SKU population
- ABC value shares reconcile to 100%
- XYZ class counts reconcile to the total SKU population

These checks help ensure that the analytical model remains internally consistent when assumptions or source data change.

## Screenshot

![Dashboard](./dashboard.png)

## Portfolio value

This project demonstrates practical Excel skills for retail inventory analytics, including:

- Inventory segmentation
- ABC analysis
- Demand variability analysis
- Replenishment calculations
- Safety-stock modeling
- Reorder-point modeling
- EOQ analysis
- Dynamic Excel formulas
- Centralized model assumptions
- Analytical validation
- Retail decision-support thinking

The project is being progressively upgraded from a basic ABC/reorder-point model into a broader **retail inventory optimization and replenishment analytics solution**.
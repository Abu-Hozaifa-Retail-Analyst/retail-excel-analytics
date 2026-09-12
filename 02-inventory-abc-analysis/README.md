# 02 · Inventory ABC Analysis & Reorder Point Model

**Business problem:** The warehouse is overstocked on low-value SKUs and
stocking out on high-value ones, because every SKU is managed with the same
review cadence and safety-stock rule. Not all 20 SKUs deserve equal
attention — a small number drive most of the inventory value and need
tighter control, while the rest can run leaner.

## File

[`inventory_abc_analysis.xlsx`](./inventory_abc_analysis.xlsx)

## Excel techniques used

- `SUMPRODUCT` for a sort-free cumulative-value running total
- `RANK` to order SKUs by annual usage value without physically re-sorting the table
- Nested `IF` classification into A/B/C tiers based on cumulative revenue share
- Differentiated safety-stock formulas by tier (tighter service level for A-items)
- Reorder point and EOQ (Economic Order Quantity) formulas
- Conditional formatting to flag class and reorder urgency at a glance
- Pareto-style dashboard chart (bar of value + cumulative % line)

## Sheet guide

| Sheet | Purpose |
|---|---|
| `Dashboard` | Pareto chart + ABC/reorder KPI summary — start here |
| `SKU Data` | 20-SKU input table (blue cells = editable assumptions) |
| `ABC Analysis` | Usage value, rank, cumulative %, and A/B/C class per SKU |
| `Reorder Point Model` | Safety stock, reorder point, and EOQ per SKU |

## Method

- **Annual Usage Value** = Unit Cost × Annual Units Sold, per SKU.
- SKUs are ranked by usage value and their cumulative share of total value is
  computed with `SUMPRODUCT` — no manual sorting needed, so the table stays
  reorderable and still classifies correctly.
- **Class A** = SKUs making up the top 80% of cumulative value (tightest
  control, ~99% service level). **Class B** = next 15% (~95% service level).
  **Class C** = remaining 5% (~90% service level, reviewed least often).
  Thresholds are editable on the `ABC Analysis` sheet.
- **Reorder Point** = (Avg Daily Demand × Lead Time) + Safety Stock, where
  Safety Stock = Z × Demand Std Dev × √Lead Time.
- **EOQ** = √(2 × Annual Demand × Order Cost ÷ Holding Cost) — the order
  quantity that minimizes total ordering + holding cost.

## Key insights found

*(from the synthetic dataset — replace with real findings once live inventory data is loaded)*

- **8 of 20 SKUs (40%) are Class A** and account for **~78.5% of total
  annual usage value** — close to the classic 80/20 split, confirming these
  are the SKUs worth the tightest stock control.
- **Fitness Tracker Band** (Electronics) is both the single highest-value SKU
  and the one with the highest reorder point — it has the longest lead time
  (45 days) in the dataset, which compounds its inventory risk and makes it
  the clearest candidate for supplier renegotiation or a backup source.
- Class C SKUs (6 of 20) represent only ~5.7% of value — a good candidate
  set for looser reorder rules or bulk/infrequent ordering to cut admin overhead.

## Data note

`SKU Data` is a synthetic dataset (seeded random generation). Unit costs and
prices are shared with `01-sales-dashboard` for portfolio continuity; annual
demand, demand variability, lead time, order cost, and holding cost are
illustrative assumptions, not real supplier data. Swap in real values with
the same column layout and every downstream sheet recalculates automatically.

## Screenshot

<<<<<<< HEAD
![Dashboard](./dashboard.png)
=======
*(add a screenshot or GIF of the Dashboard sheet here)*
>>>>>>> d6edb06c3802f9db7265119b6b7630d5cd1e44e6

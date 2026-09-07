# Retail Profitability & Revenue Leakage Intelligence System
### Business Insights & Recommendations

**Tech Stack:** Oracle SQL Developer (data modeling, analysis) · Microsoft Excel 2021 (Power Query, Power Pivot, DAX, PivotTables, interactive dashboard)
**Dataset:** 2,000 orders across 24 months, 8 relational tables, 34 products, 8 store locations

---

## Executive Summary

This project analyzes a simulated retail dataset to uncover hidden sources of revenue leakage — money lost not through low sales, but through inefficiencies in discounting, returns, and inventory management. Using SQL for data modeling and analysis, and Excel for interactive visualization, the analysis identified **₹1,15,61,497.56 in total revenue leakage**, broken down across three major sources:

| Leakage Source | Amount | % of Total Leakage |
|---|---:|---:|
| Dead Stock (never-sold inventory) | ₹78,69,491.78 | 68.1% |
| Discount Over-Extension | ₹22,13,532.11 | 19.1% |
| Product Returns | ₹14,78,473.67 | 12.8% |
| **Total** | **₹1,15,61,497.56** | **100%** |

Each of these was traced to a specific, addressable root cause rather than being spread evenly across the business — meaning targeted fixes, not broad cost-cutting, are the right response.

---

## Finding 1: Dead Stock Is the Single Largest Leak

**₹78,69,491.78 tied up in inventory that has never sold a single unit**, across just 3 products out of 34 (Fondue Set, Fax Machine Adapter, Retro Film Camera).

This is the largest leakage category by far — nearly 3.5x larger than discount leakage and 5x larger than return losses combined — yet it's also the easiest to act on, since it involves no customer behavior change, only inventory decisions.

**Recommendation:** Liquidate or heavily discount these 3 SKUs to recover partial capital, and audit procurement decisions that led to stocking products with zero demonstrated demand before reordering similar items.

---

## Finding 2: One Store Is Discounting Nearly 4x More Than Peers

**Koramangala Outlet discounts at an average of 33.69%**, compared to roughly 8% across all other stores — resulting in **₹7,23,086.40** in discount leakage from that single location, the largest individual contributor to the ₹22,13,532.11 total discount leakage.

This gap is too large to be routine promotional activity and points to either a local pricing/authorization control gap or inconsistent discount policy enforcement at that location specifically.

**Recommendation:** Audit Koramangala Outlet's discount approval process and point-of-sale discount controls. Standardizing this one store's practices to match the ~8% network average would recover the majority of this leakage source.

---

## Finding 3: Beauty Category Has a Return Rate 3-6x Higher Than Any Other Category

**Beauty products are returned at a 25.2% rate**, versus 4-7% across every other category — driving **₹5,35,441** in refund losses from Beauty alone, out of ₹14,78,473.67 in total return losses.

A return rate this far outside the norm for one category, rather than spread evenly, typically signals a specific product quality issue, inaccurate product descriptions/images, or a packaging/shipping damage problem particular to that category.

**Recommendation:** Conduct a root-cause review of Beauty category returns — check for a pattern in which specific SKUs drive the rate, review recent customer return-reason data if available, and inspect packaging/fulfillment handling for this category specifically.

---

## Finding 4: A Top-Selling Product Is Losing Money on Every Unit Sold

**Bluetooth Speaker Pro (Value Edition)** is the highest-revenue product in the entire catalog (₹36,14,451.39) but carries a **-3.75% profit margin** — meaning the business loses money on every unit sold, even as it appears to be a top performer by revenue alone.

This is a case where a surface-level "top seller" report would completely miss the underlying problem — revenue and profitability tell two different stories for this product.

**Recommendation:** Re-price this product or renegotiate its cost basis immediately — its high sales volume means the negative margin compounds significantly. Revenue-based reporting should not be used in isolation to evaluate product performance going forward.

---

## Finding 5: A Real Revenue Dip in October 2025 (Not a Data Artifact)

Monthly revenue tracking identified a genuine **~43.76% month-over-month drop** in October 2025 (₹6,31,655 → ₹3,55,256), distinct from the artificially low partial-month reading in September 2026 (which reflects an incomplete data extraction period, not a business decline).

Distinguishing genuine anomalies from data artifacts is a key part of trustworthy reporting — treating the Sep 2026 partial month as a real decline would have produced a false alarm.

**Recommendation:** Investigate what specifically changed in October 2025 (seasonality, a stockout, a marketing pause, a competitor event) since this is a real, unexplained dip worth a dedicated follow-up analysis.

---

## Methodology Notes

- All figures were first calculated and cross-verified in **Oracle SQL Developer** (7 analytical queries: product profitability, store ranking, discount leakage, return loss, dead stock detection, monthly trend, and total leakage summary), then independently rebuilt in **Excel via Power Pivot/DAX measures** — every headline number above matches exactly between both tools, down to the rupee.
- The interactive Excel dashboard includes **cross-filtering slicers** (by store and by category) connected across multiple linked PivotCharts, allowing any of the findings above to be explored at a store- or category-specific level.

---

## Summary Recommendation Priority

| Priority | Action | Est. Recovery Potential |
|---|---|---:|
| 1 | Liquidate/discount 3 dead stock SKUs | Partial recovery of ₹78.7L tied-up capital |
| 2 | Audit Koramangala Outlet discount controls | Up to ₹7.2L/period going forward |
| 3 | Re-price or discontinue Bluetooth Speaker Pro (Value Edition) | Stops ongoing per-unit losses |
| 4 | Root-cause Beauty category returns | Up to ₹5.4L/period going forward |
| 5 | Investigate Oct 2025 revenue dip | Diagnostic — prevents recurrence |

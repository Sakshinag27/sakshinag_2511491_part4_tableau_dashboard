# Dashboard Story: Retail Sales Performance 2024–2025
## For Leadership Audience

---

## Executive Summary

Our retail business generated **₹217M in revenue and ₹33.3M in profit** across 4,200 orders over the 2024–2025 period, maintaining a healthy **15.3% overall margin**. The business is operationally sound, but a concentrated set of risks — Furniture category margin erosion, Home Office return rates, and aggressive discounting by a minority of sales reps — are suppressing profit by an estimated ₹5–8M annually. Three strategic opportunities in Technology expansion, Referral channel growth, and East region practices replication could accelerate growth significantly.

---

## What Is Performing Well

**Technology is the growth engine.** At an 18.2% margin and ₹28M in profit contribution (71% of total profit), Technology — led by Copiers, Accessories, and Phones — is significantly outperforming the rest of the portfolio. The average Technology order value far exceeds Furniture or Office Supplies. This category requires investment protection, not restructuring.

**The South and North regions are holding strong.** Together, South (₹64.7M) and North (₹54.6M) contribute 55% of total sales. South leads in volume; East leads in margin efficiency at 15.6%, consistently outperforming other regions in profit-per-rupee-sold.

**Organic acquisition is working at scale.** With 1,694 orders and ₹88.8M in sales, Organic is the backbone of our customer acquisition. Monthly sales trends show recovery in H2 2025 (Jul–Nov averaging ₹10M+), suggesting positive momentum.

**Same Day shipping correlates with lower returns.** Orders delivered same day carry only a 3.0% return rate versus 5.0% for all other delivery tiers, reinforcing the value of fulfillment speed for high-stakes orders.

---

## What Is Underperforming

**Furniture is a structural problem.** Despite ₹51.6M in sales, Furniture contributes only ₹3.6M in profit (6.9% margin). Tables and Bookcases sit at 5.7% margin — the lowest in the entire portfolio. Combined with a 7.7% return rate (more than double Technology), Furniture's real profitability is likely negative when return logistics are factored in.

**Home Office customers return products at an alarming rate.** At 5.7% returns — 46% higher than Consumer and Corporate — the Home Office segment's high revenue (₹74.5M) masks a retention and satisfaction gap. These are likely our most margin-diluting customers if return costs are included.

**April and Q2 consistently underperform.** Both 2024 and 2025 show a pronounced dip in April sales. This is not random noise — it is a structural Q2 weakness that requires proactive intervention.

**The West region is the laggard.** Lowest absolute profit (₹7.4M), lowest margin (15.1%), and lowest order volume suggest either an underserved market or an execution gap in sales or marketing.

---

## What Risks Are Visible

**Discount discipline is breaking down at the margins.** While 64 orders (1.5%) sit in the 31–35% discount bracket, they collectively generate losses of –₹102,494. More concerning, the 1,086 orders at 21–30% discount average only ₹3,181 profit — a 76% reduction from undiscounted orders. If this trend grows, overall margin will compress significantly.

**Furniture returns carry hidden costs.** The ₹3.6M profit figure for Furniture does not account for reverse logistics, restocking labor, or inventory write-downs from returned large items. The real Furniture P&L could be materially worse.

**Organic channel dependency is a concentration risk.** With 40% of all orders from a single acquisition channel, any disruption to organic search visibility or brand recognition could materially impact revenue with limited ability to pivot quickly.

**No customer-level data means churn is invisible.** We cannot currently identify repeat vs. one-time customers, limiting our ability to model lifetime value or detect early churn signals.

---

## What Opportunities Are Visible

**East region practices can be exported.** The East region's superior margin (15.6%) on similar order counts to the West (897 vs 1,037 orders) suggests better pricing or discount discipline. Codifying and replicating this approach in the West could add ₹500K–₹1M in profit annually.

**Referral and Social channels punch above their weight.** Both channels deliver 15.7–15.8% margins versus 15.1% for Organic and Paid. Growing Referral from 392 to 600+ orders and increasing Social investment in Technology could shift the mix toward higher-margin acquisition.

**Same Day and First Class shipping can be used as a retention lever.** Offering premium shipping for high-value Technology orders (>₹50K) could reduce returns and improve customer satisfaction scores, particularly in the Home Office segment.

**Technology sub-categories have expansion headroom.** Copiers at ₹40.6M, Accessories at ₹39.2M, and Phones at ₹38.4M are all near-equal contributors. Accessory attach rates to Machines, Phones, and Copiers represent a low-cost upsell opportunity if bundled at point of sale.

---

## Recommended Business Actions

| Priority | Action | Expected Impact |
|----------|--------|----------------|
| **1 — Immediate** | Cap discounts at 25% without VP approval; review all 30%+ discount orders | Protect ₹3–5M annual profit |
| **2 — Q1** | Launch Furniture return reduction program (better imagery, sizing guides, restocking fee for >₹10K orders) | Reduce 7.7% return rate toward 4% |
| **3 — Q1** | Activate Q2 promotional campaign for Corporate/Home Office customers in March | Offset April seasonal dip |
| **4 — Q2** | Build formal Referral program with incentives | Grow channel to 600+ orders |
| **5 — Q2** | Study East region account management practices; deploy in West | +₹500K–1M profit |
| **6 — Ongoing** | Offer Same Day/First Class upgrades for Technology orders >₹50K | Reduce returns, improve NPS |

---

## Limitations of This Dashboard

- **Return costs are understated:** The `profit` field does not capture reverse logistics, restocking, or write-down costs for returned items. Furniture profitability is likely materially worse than shown.
- **No customer-level LTV:** Without linking orders to unique customers over time, we cannot assess loyalty, churn, or lifetime value.
- **Campaign channel has missing values:** Approximately 24 orders have no campaign channel recorded, indicating a data capture gap in the CRM or checkout flow.
- **Dates are Excel serial numbers in source data:** Date fields required conversion and should be validated for any downstream Tableau publish.
- **Customer rating is not yet used:** The `customer_rating` field (avg 4.0/5.0) was collected but not incorporated into dashboard views due to insufficient segmentation; a rating-by-category view could be valuable in a follow-up iteration.

---

## Suggested Next Analysis

1. **Customer cohort analysis** — Link `customer_id` across orders to identify repeat purchase rates, AOV growth, and churn by segment.
2. **Return cost modeling** — Attach estimated reverse logistics costs to returned orders to get true Furniture P&L.
3. **Discount approval audit** — Map all 30%+ discount orders to sales reps and managers; identify patterns.
4. **Technology accessory attach rate** — Analyze whether Accessories are sold alongside Machines, Phones, or Copiers or as standalone; optimize bundling.
5. **State-level drill-down** — The state field is rich; a state-level heat map could reveal hyper-local growth pockets or underserved markets within each region.

---

*Dashboard prepared by: Business Analytics Team | Data period: Jan 2024 – Dec 2025 | 4,200 orders | ₹217M revenue*

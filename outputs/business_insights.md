# Business Insights Report
## Executive Dashboard — Retail Sales Performance (2024–2025)

---

### Calculated Fields Reference

| Field | Logic | Purpose |
|-------|-------|---------|
| **Profit Margin** | `Profit / Sales` | Measures operational efficiency per order |
| **Cost** | `Sales - Profit` | Derives cost of goods and operations |
| **Average Order Value** | `SUM(Sales) / COUNT(Orders)` | Tracks revenue intensity per transaction |
| **Return Rate** | `SUM(Return Flag) / COUNT(Orders)` | Measures customer dissatisfaction signal |
| **Shipping Delay Bucket** | `IF delivery_days = 0 THEN "Same Day" ELSEIF delivery_days <= 2 THEN "Fast (1–2d)" ELSEIF delivery_days <= 5 THEN "Standard (3–5d)" ELSE "Slow (6–9d)"` | Groups delivery performance into actionable tiers |

---

## 8 Business Insights

---

### Insight 1 — Sales Trend: Seasonal Dips in April and August Demand Attention

**Observation:** Monthly sales show recurring dips in April (₹8.0M in 2024, ₹7.2M in 2025) and August (₹6.3M in 2024, ₹10.9M in 2025). July–August 2025 showed strong recovery to ₹10.7M–₹10.9M, suggesting improving momentum.

**Data Evidence:** April 2024 = ₹8.0M vs Jan 2024 = ₹9.4M (–15%); April 2025 = ₹7.2M vs March 2025 = ₹10.2M (–29.5%).

**Business Interpretation:** April dips may reflect post-Q1 budget exhaustion in Corporate and Home Office segments. The consistent pattern suggests a structural lull, not a one-off.

**Recommended Action:** Launch targeted Q2 promotions in March–April for Corporate customers. Consider bundled deals on high-margin Technology products to soften the seasonal trough.

---

### Insight 2 — Regional Performance: South Leads in Sales, East Leads in Margin

**Observation:** The South region generates the highest sales (₹64.7M, 29.8% of total) but the East region achieves the highest profit margin (15.6%). The West region is the lowest performer on both sales (₹48.9M) and margin (15.1%).

**Data Evidence:** South: ₹64.7M sales, ₹10.0M profit (15.4% margin). East: ₹48.9M sales, ₹7.6M profit (15.6% margin). West: ₹48.9M sales, ₹7.4M profit (15.1% margin).

**Business Interpretation:** The East region's superior margin suggests better discount discipline or a more profitable product mix despite lower overall volume. The South's high sales volume may be diluted by heavier discounting.

**Recommended Action:** Study the East region's account management and discount approval practices and replicate them in the West. Explore West region demand drivers — marketing investment may be underperforming.

---

### Insight 3 — Category Profitability: Technology Carries the Business; Furniture is a Concern

**Observation:** Technology accounts for 70.9% of total profit (₹28.0M) on only 33% of orders, delivering an 18.2% margin. Furniture, despite generating ₹51.6M in sales (23.8% of total), contributes only ₹3.6M in profit — a thin 6.9% margin.

**Data Evidence:** Technology margin: 18.2%. Furniture margin: 6.9%. Office Supplies margin: 14.9%. Technology's AOV is dramatically higher due to Copiers, Accessories, and Phones sub-categories.

**Business Interpretation:** Furniture's low margin is driven by the Bookcases and Tables sub-categories (both at 5.7% margin), likely due to high discounting and logistical costs on bulky items.

**Recommended Action:** Review Furniture pricing strategy — particularly Tables and Bookcases. Consider reducing discount authority on these sub-categories. Redirect sales incentives toward Technology upsells.

---

### Insight 4 — Customer Segment: Home Office Has the Highest Returns and Requires Priority Attention

**Observation:** Home Office segment generates the most revenue (₹74.5M) but carries a 5.7% return rate — significantly higher than Consumer (3.9%) and Corporate (4.0%).

**Data Evidence:** Home Office: 82 returns out of 1,446 orders (5.7%). Corporate: 56 / 1,399 (4.0%). Consumer: 53 / 1,355 (3.9%).

**Business Interpretation:** Home Office customers may be purchasing speculatively without firm organizational need, leading to higher returns. This segment also shows strong revenue, making retention critical.

**Recommended Action:** Implement a post-purchase engagement workflow for Home Office customers (order confirmation, usage guides, onboarding). Review which specific products are being returned most and add detailed product descriptions.

---

### Insight 5 — Discount Impact: Heavy Discounting Destroys Profitability

**Observation:** Orders with no discount average ₹13,203 profit per order. Orders discounted 31–35% average a loss of –₹1,601 per order. Average profit drops monotonically as discount increases.

**Data Evidence:**
- 0% discount: 1,024 orders, avg profit ₹13,203
- 1–10%: 979 orders, avg profit ₹10,010
- 11–20%: 1,047 orders, avg profit ₹6,336
- 21–30%: 1,086 orders, avg profit ₹3,181
- 31–35%: 64 orders, avg profit –₹1,601

**Business Interpretation:** Discounts above 30% generate losses. With 64 orders in this bracket, total losses from over-discounting are –₹102,494. While small in absolute terms, the pattern signals a discipline problem in discount approvals.

**Recommended Action:** Cap maximum discount authority at 25% without VP approval. Flag all 30%+ discounts for immediate manager review. Build discount impact into sales rep performance metrics.

---

### Insight 6 — Shipping Performance: Standard Class Dominates but Same Day is Most Efficient

**Observation:** Standard Class handles 58% of all orders (2,435) with an average delivery of 4.71 days and a 15.5% margin. Same Day shipping has only 241 orders but delivers on average in 0.4 days with a comparable 15.1% margin.

**Data Evidence:** Standard Class: ₹122.8M sales, 4.71 avg days. Same Day: ₹14.6M, 0.4 avg days. Return rates by delay tier: Same Day = 3.0%, Fast/Standard/Slow all = 5.0%.

**Business Interpretation:** Same Day delivery correlates with lower return rates (3.0% vs 5.0%), suggesting faster fulfillment increases satisfaction. However, Standard Class is the workhorse and its 4.71-day average is acceptable for most customers.

**Recommended Action:** Promote Same Day and First Class shipping for high-value Technology orders above ₹50,000. Monitor whether faster delivery reduces returns in the Furniture category, where returns are most costly.

---

### Insight 7 — Return Patterns: Furniture Returns Are a Disproportionate Risk

**Observation:** Furniture has a 7.7% return rate — more than double Technology's 3.0% and nearly double Office Supplies' 3.7%. Given Furniture's already thin 6.9% margin, returns further erode profitability.

**Data Evidence:** Furniture: 88 returns / 1,147 orders = 7.7%. Office Supplies: 61 / 1,669 = 3.7%. Technology: 42 / 1,384 = 3.0%. Combined with Furniture's 5.7% margin on Tables and Bookcases, returns make these sub-categories economically marginal.

**Business Interpretation:** Furniture returns likely involve logistical reversal costs (pickup, repackaging, restocking) that are not captured in the profit column — making the real loss per return significantly higher than shown.

**Recommended Action:** Introduce a restocking fee or stricter return window for Furniture over ₹10,000. Improve product imagery and sizing guides to reduce "not as expected" returns. Explore B2B channel partnerships for Furniture to reduce consumer returns.

---

### Insight 8 — Business Risk & Opportunity: Organic Channel Dominates but Social and Referral Have Higher Margins

**Observation:** Organic is the highest-volume channel (1,694 orders, ₹88.8M sales), but Social (15.8% margin) and Referral (15.7% margin) outperform it on profitability per rupee of revenue.

**Data Evidence:** Organic margin: 15.1%. Email: 15.5%. Social: 15.8%. Referral: 15.7%. Paid: 15.1%.

**Business Interpretation:** Referral and Social channels, while smaller in volume, attract customers with slightly better product mix or pricing discipline. Referral customers may also have lower return rates due to pre-qualified intent.

**Recommended Action:** Build a formal referral program with incentives to grow the Referral channel from 392 to 600+ orders. Increase investment in Social media for the Technology category where margins are already strong. Track return rates and LTV by channel to validate.

---

*Data covers 4,200 orders across 2024–2025. Total revenue: ₹217.0M. Total profit: ₹33.3M. Overall margin: 15.3%.*

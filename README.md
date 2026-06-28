# Retail Sales Executive Dashboard
## README

---

## Business Problem Summary

The retail leadership team needs a single executive-grade dashboard to monitor sales performance, profitability, customer segment behavior, category performance, shipping operations, discount impact, and return patterns across two fiscal years (2024–2025). The dashboard must not just report data — it must tell a business story that helps leadership identify risks, opportunities, and recommended actions.

---

## Dataset Description

**File:** `dashboard_sales_data.xlsx`
**Records:** 4,200 orders
**Date range:** January 1, 2024 – December 31, 2025
**Geographic scope:** India (5 regions: North, South, East, West)
**Total revenue:** ₹217.0M
**Total profit:** ₹33.3M

### Fields

| Field | Type | Description |
|-------|------|-------------|
| order_id | String | Unique order identifier |
| order_date | Date | Order placement date |
| ship_date | Date | Shipment date |
| customer_id | String | Customer identifier |
| customer_segment | String | Home Office / Corporate / Consumer |
| region | String | North / South / East / West |
| state | String | Indian state |
| city | String | City |
| category | String | Furniture / Office Supplies / Technology |
| sub_category | String | 13 sub-categories |
| product_name | String | Product name with SKU |
| ship_mode | String | Same Day / First Class / Second Class / Standard Class |
| sales | Decimal | Order revenue (₹) |
| quantity | Integer | Units ordered |
| discount | Decimal | Discount fraction (0–0.35) |
| profit | Decimal | Net profit (₹); can be negative |
| return_flag | Binary (0/1) | 1 = order was returned |
| delivery_days | Integer | Days from order to ship |
| customer_rating | Decimal | Customer satisfaction (1–5 scale) |
| campaign_channel | String | Organic / Paid / Email / Social / Referral |

---

## Calculated Fields Created

| Name | Formula (Tableau) | Description |
|------|--------------------|-------------|
| **Profit Margin** | `SUM([Profit]) / SUM([Sales])` | Profitability ratio per order or aggregate |
| **Cost** | `SUM([Sales]) - SUM([Profit])` | Derives cost of goods + operations |
| **Average Order Value** | `SUM([Sales]) / COUNTD([Order Id])` | Revenue per unique order |
| **Return Rate** | `SUM([Return Flag]) / COUNT([Order Id])` | % of orders returned |
| **Shipping Delay Bucket** | `IF [Delivery Days] = 0 THEN "Same Day" ELSEIF [Delivery Days] <= 2 THEN "Fast (1-2d)" ELSEIF [Delivery Days] <= 5 THEN "Standard (3-5d)" ELSE "Slow (6-9d)" END` | Actionable delivery tier |
| **Discount Bucket** | `IF [Discount] = 0 THEN "No Discount" ELSEIF [Discount] <= 0.1 THEN "1-10%" ELSEIF [Discount] <= 0.2 THEN "11-20%" ELSEIF [Discount] <= 0.3 THEN "21-30%" ELSE "31-35%" END` | Discount tier for profitability analysis |
| **Profit per Order** | `SUM([Profit]) / COUNT([Order Id])` | Average profit per transaction |
| **YoY Sales Growth** | `(SUM([Sales]) - LOOKUP(SUM([Sales]), -12)) / ABS(LOOKUP(SUM([Sales]), -12))` | Year-over-year sales growth % |

---

## Dashboard Components

### Executive Dashboard (Main View)

**KPI Cards (top row):**
- Total Revenue: ₹217.0M
- Overall Profit Margin: 15.3%
- Return Rate: 4.5%
- Average Order Value: ₹51,671

**Charts included:**
1. Monthly Sales & Profit Trend (line chart, 24 months)
2. Regional Sales & Profit Bar Chart (horizontal bars)
3. Category Profitability Treemap (size = Sales, color = Margin)
4. Customer Segment Comparison (grouped bars + return rate overlay)
5. Discount vs. Profit Scatter Plot (all 4,200 orders)
6. Shipping Mode Performance (bars + delivery day labels)
7. Return Rate Heat Table (Category × Region)

### Supporting Detail Sheets
- `Sales Trend View` — full 24-month line chart with annotations
- `Regional Performance View` — region + state level map and bar
- `Category Profitability View` — treemap + sub-category bar chart
- `Customer Segment View` — segment comparison with return overlay
- `Shipping Performance View` — ship mode bars + delay distribution
- `Discount vs Profit View` — scatter plot with trend line
- `Return Analysis View` — heat table + category return bar chart

---

## Filters and Interactions

### Global Filters (apply to entire dashboard):
- **Region** — filter by North / South / East / West
- **Category** — filter by Furniture / Office Supplies / Technology
- **Customer Segment** — filter by Home Office / Corporate / Consumer
- **Date Range** — filter by order_date (slider or date picker)
- **Ship Mode** — filter by shipping method
- **Campaign Channel** — filter by Organic / Paid / Email / Social / Referral

### Dashboard Actions:
- **Click on Region bar** → filters all other charts to that region
- **Click on Category in Treemap** → filters segment and shipping views
- **Hover on scatter plot point** → tooltip shows Order ID, Product, Discount %, Profit

---

## Key Business Insights (Summary)

1. **Technology drives 71% of profit** at 18.2% margin — the business's core engine
2. **Furniture is a margin risk** — 6.9% margin with 7.7% return rate; Tables & Bookcases at 5.7% margin
3. **Discounts above 25% destroy profitability** — 31–35% discount orders average –₹1,601 per order
4. **Home Office segment has highest returns** — 5.7% vs. 3.9–4.0% for other segments
5. **April is a structural weak point** — consistent dip in both 2024 and 2025
6. **East region leads in margin efficiency** — 15.6% vs. West's 15.1% with similar order counts
7. **Referral and Social channels have the best margins** — 15.7–15.8% vs. 15.1% Organic
8. **Same Day delivery reduces returns** — 3.0% return rate vs. 5.0% for slower shipping

---

## Dashboard Story Summary

The business is profitable and growing in H2 2025, but faces concentrated risks in Furniture profitability, Home Office returns, and discount discipline. Technology is the undisputed profit driver and should be protected and expanded. The East region's superior margin practices should be studied and replicated. Quick wins are available through discount cap policies and a targeted Q2 promotional campaign. See `outputs/dashboard_story.md` for the full leadership narrative.

---

## Assumptions and Limitations

- `order_date` and `ship_date` fields in Excel were stored as Excel serial numbers; these were parsed correctly in Python/Tableau but should be validated on first open
- `delivery_days` is calculated as ship_date minus order_date; Same Day = 0 is treated as correct (not an error)
- `profit` does not include return logistics costs; Furniture profitability is likely overstated
- `campaign_channel` has ~24 null values; these are excluded from channel analysis
- Return costs are assumed to be zero in all profit calculations (conservative limitation)
- No customer-level linkage is available; LTV and churn analysis are not possible with this dataset
- Currency assumed to be Indian Rupees (₹) throughout

---

## Screenshots Included

| File | Description |
|------|-------------|
| `screenshots/full_dashboard.png` | Complete executive dashboard view |
| `screenshots/sales_trend_view.png` | 24-month sales and profit trend |
| `screenshots/regional_performance_view.png` | Regional bar chart with margin labels |
| `screenshots/category_profitability_view.png` | Category treemap |
| `screenshots/filter_interaction_view.png` | Dashboard with Technology filter active |

---

## Output Files

| File | Description |
|------|-------------|
| `outputs/business_insights.md` | 8 structured business insights with evidence and actions |
| `outputs/dashboard_story.md` | Leadership narrative connecting all dashboard views |
| `outputs/chart_selection_justification.md` | Rationale for each chart type and design decision |
| `README.md` | This file |

---

*Prepared by: Business Analytics Team | June 2026*

# Chart Selection Justification
## Executive Dashboard — Retail Sales Performance 2024–2025

---

## Overview

This document explains the rationale behind every major chart in the executive dashboard. Each selection is driven by the business question it answers, the nature of the data being displayed, and adherence to visualization best practices.

---

## 1. Sales Trend — Line Chart (Monthly)

**Business question answered:** How are sales and profit changing over time? Are there seasonal patterns?

**Why this chart type:** Line charts are the canonical choice for continuous time-series data. They make slope (rate of change), seasonal patterns, and inflection points immediately visible. A bar chart of monthly data would obscure trend direction; a scatter plot would imply independence between time points.

**Fields used:**
- X-axis: Order Date (Month/Year)
- Y-axis: SUM(Sales), SUM(Profit)
- Color: Measure name (two lines — Sales in blue, Profit in teal)

**Design principle applied:** Dual-measure lines with a shared axis allow comparison of revenue vs. profit trajectory without distorting either scale. Annotations mark the April dips to draw leadership attention to the seasonal pattern.

**Mistake avoided:** Did not use a bar chart, which would make it harder to see the continuous trend and would visually suggest each month is independent. Did not use a cumulative line, which would mask the monthly dip.

---

## 2. Regional Performance — Horizontal Bar Chart

**Business question answered:** Which region drives the most sales and profit? Where are we over/underperforming?

**Why this chart type:** Horizontal bar charts are ideal for comparing a single quantitative measure across a small number of categorical groups (4 regions). The horizontal orientation allows region labels to be read without rotation. A map would be appropriate if states were shown, but at the region level, positional encoding is more precise than geographic area.

**Fields used:**
- Bars: SUM(Sales) and SUM(Profit) side-by-side
- Y-axis: Region
- Color: Metric type (Sales vs. Profit)
- Labels: Margin % on each profit bar

**Design principle applied:** Sorting by descending sales surfaces the highest-value region first. Profit margin labels on bars give leadership the ratio they care about without requiring mental division.

**Mistake avoided:** Did not use a pie chart (makes part-to-total comparison difficult and hides absolute values). Did not use a map at the region level (four polygons convey little geographic insight).

---

## 3. Category & Sub-Category Profitability — Treemap

**Business question answered:** Which categories and sub-categories drive or destroy profit? What is the size vs. profitability relationship?

**Why this chart type:** A treemap encodes two variables simultaneously — area encodes revenue magnitude (Sales) and color encodes profit margin. This makes it immediately apparent when a large-revenue sub-category has poor margins (e.g., Tables: large box, cool/red color). A stacked bar chart could show the same data but would not convey the size-vs-margin relationship as intuitively.

**Fields used:**
- Size: SUM(Sales) — hierarchy: Category > Sub-Category
- Color: Profit Margin (diverging palette: red for low/negative, green for high)
- Label: Sub-category name + margin %

**Design principle applied:** Diverging color palette centered at the portfolio average (15.3%) makes above/below-average margins instantly distinguishable. Labels are white for legibility inside colored boxes.

**Mistake avoided:** Did not use a 3D chart. Did not use rainbow colors (used a semantically meaningful diverging scale). Did not show only one level of hierarchy — Category alone would hide the critical sub-category differences.

---

## 4. Customer Segment Comparison — Grouped Bar Chart

**Business question answered:** How do segments compare on revenue, profit, and return behavior?

**Why this chart type:** Grouped bar charts allow side-by-side comparison of multiple metrics across a small number of groups. With three segments and three measures (Sales, Profit, Return Rate), grouping makes the comparisons across all three simultaneously visible. A table would present the numbers but suppress visual comparison.

**Fields used:**
- X-axis: Customer Segment
- Y-axis (primary): SUM(Sales)
- Color: Segment
- Secondary axis or label: Return Rate %
- Size of bars differentiated by measure

**Design principle applied:** Return Rate is displayed as a line/dot overlay on the same chart to avoid requiring a separate chart. The visual contrast between bar (volume) and dot (rate) helps leadership immediately see the Home Office paradox: highest sales, highest returns.

**Mistake avoided:** Did not use a scatter plot (too many points would overlap). Did not show only revenue without the return context, which would create an incomplete and misleading picture of segment health.

---

## 5. Discount vs. Profit — Scatter Plot

**Business question answered:** Is there a relationship between discount level and order profitability? At what discount level does profitability collapse?

**Why this chart type:** A scatter plot is the only chart type that directly shows the relationship between two continuous variables (Discount and Profit) across all individual orders. It reveals distribution, outliers, and the threshold effect where high discounts flip profit negative. A bar chart of average profit by discount bucket would show the trend but hide the variance and individual order patterns.

**Fields used:**
- X-axis: Discount (0 to 0.35)
- Y-axis: Profit (per order)
- Color: Category (Furniture, Technology, Office Supplies)
- Reference line: Y = 0 (profitability threshold)
- Trend line: Linear regression

**Design principle applied:** A red reference line at Profit = 0 makes the breakeven point visually prominent. Color by Category reveals which category drives losses at high discounts (Furniture at 30%+ discount frequently goes negative).

**Mistake avoided:** Did not aggregate to averages only — keeping individual points preserves the distribution and variance story. Did not use a line chart (discount is not a time variable; each order is independent).

---

## 6. Shipping Performance — Bar Chart with Reference Line

**Business question answered:** Which shipping mode delivers the best balance of speed, volume, and profitability? Where are delivery delays concentrated?

**Why this chart type:** A bar chart grouped by Ship Mode, with average delivery days as a secondary measure, makes the speed-volume-margin tradeoff immediately visible. The addition of delivery delay distribution as a stacked bar shows where Standard Class delivery days cluster.

**Fields used:**
- X-axis: Ship Mode
- Y-axis (primary): Order count / SUM(Sales)
- Color: Delivery Delay Bucket (Same Day, Fast, Standard, Slow)
- Label: Average delivery days per ship mode

**Design principle applied:** Sorting by average delivery speed (ascending) allows the viewer to track the speed-cost-margin tradeoff from left to right. This reduces cognitive load compared to alphabetical sorting.

**Mistake avoided:** Did not use a pie chart for ship mode volume (bars are more precise). Did not omit the delivery day context — without it, the chart only shows revenue, not operational performance.

---

## 7. Return Analysis — Heat Table / Highlight Table

**Business question answered:** Where are returns concentrated? Which category-region or category-segment combination has the worst return profile?

**Why this chart type:** A highlight table (cross-tab with color) is the most efficient way to show a two-dimensional matrix of return rates. With 3 categories × 4 regions (or 3 segments), a heat table fits on one screen and makes hotspots visually obvious. Individual bar charts for each category or region would require 7 separate charts and more page space.

**Fields used:**
- Rows: Category
- Columns: Region (or Segment)
- Color: Return Rate % (sequential palette: white to red)
- Label: Return count and rate %

**Design principle applied:** Sequential color palette (white to red) encodes increasing return risk clearly. Darker red = higher alert. Labels preserve the exact numbers for leadership who need to report specifics.

**Mistake avoided:** Did not use absolute return counts without rates (a region with 10x more orders would appear worse even if its return rate was lower). Used rate, not count.

---

## KPI Cards Design Rationale

**Three KPI cards shown: Total Revenue, Profit Margin, Return Rate**

These three are chosen because they represent the three most important questions a retail CEO asks:
1. *How much did we sell?* → Total Revenue
2. *How efficiently?* → Profit Margin
3. *How satisfied are customers?* → Return Rate

Displaying them as large-number cards at the top of the dashboard ensures leadership reads the headline story before any chart. Each card includes period-over-period comparison to show direction, not just level.

**Mistake avoided:** Did not include 10+ KPI cards (dashboard fatigue). Did not include operational metrics (e.g., average delivery days) in the KPI tier — those belong in the shipping detail view.

---

## Color Palette Rationale

| Color | Usage | Semantic meaning |
|-------|-------|-----------------|
| Deep Navy (#1B2A4A) | Primary bars, headers | Authority, data anchoring |
| Teal (#2EC4B6) | Profit lines, positive indicators | Growth, positive momentum |
| Amber (#F4A261) | Warnings, Home Office segment | Caution, attention |
| Coral/Red (#E63946) | Losses, high return rates | Risk, negative |
| Light Gray (#F8F9FA) | Background, grid lines | Neutral canvas |

The palette avoids rainbow colors, is partially colorblind-safe (the red-teal pair is accessible for deuteranopia), and uses semantic associations (red = risk, teal = positive).

---

*Chart selection principles applied from: Few, S. "Show Me the Numbers" (2012); Tufte, E. "The Visual Display of Quantitative Information" (2001)*

# Name - AjaySingh
# Id - Bitsom_Ba_2511011


---

## 1. Business Problem Summary

The retail leadership team required an executive dashboard to monitor and evaluate business performance across sales, profitability, customer segments, regional markets, shipping operations, discount impact, and return patterns. The goal was to move beyond static reports and enable data-driven decision-making through interactive visualizations that tell a clear business story.

---

## 2. Dataset Description

**File:** `data/dashboard_sales_data.xlsx`

| Field | Type | Description |
|-------|------|-------------|
| order_id | Categorical | Unique order identifier |
| order_date | Date | Date order was placed |
| ship_date | Date | Date order was shipped |
| customer_id | Categorical | Unique customer identifier |
| customer_segment | Categorical | Consumer, Corporate, Home Office |
| region | Categorical | North, South, East, West |
| state | Geographic | Indian state |
| city | Geographic | City of delivery |
| category | Categorical | Furniture, Office Supplies, Technology |
| sub_category | Categorical | 13 product sub-categories |
| ship_mode | Categorical | Same Day, First Class, Second Class, Standard Class |
| sales | Numerical | Revenue per order (₹) |
| quantity | Numerical | Units ordered |
| discount | Numerical | Discount applied (0–0.35) |
| profit | Numerical | Profit per order (₹) |
| return_flag | Binary | 1 = Returned, 0 = Not returned |
| delivery_days | Numerical | Days from order to delivery |
| customer_rating | Numerical | Customer satisfaction rating (1–5) |
| campaign_channel | Categorical | Organic, Paid, Social, Email, Referral |

**Total Records:** 4,200 orders

---

## 3. Tableau Workbook Description

**File:** `tableau/executive_dashboard.twbx`

The workbook contains 7 analytical worksheets and 1 executive dashboard built on the dataset above. All sheets are interconnected through dashboard filters and action filters to enable cross-chart interactivity.

---

## 4. Calculated Fields Created

| Field Name | Formula | Purpose |
|-----------|---------|---------|
| Profit Margin | `SUM(Profit) / SUM(Sales)` | Measures profitability efficiency |
| Cost | `SUM(Sales) - SUM(Profit)` | Determines cost of goods sold |
| Average Order Value | `SUM(Sales) / COUNTD(Order Id)` | Measures revenue per transaction |
| Return Rate | `SUM(Return Flag) / COUNT(Order Id)` | Tracks return frequency |
| Shipping Delay Bucket | `IF [Delivery Days] <= 2 THEN "Fast Delivery (0-2 Days)" ELSEIF [Delivery Days] <= 5 THEN "Standard Delivery (3-5 Days)" ELSE "Delayed Delivery (5+ Days)" END` | Categorizes delivery performance |

---

## 5. Dashboard Components

| Sheet | Chart Type | Business Purpose |
|-------|-----------|-----------------|
| Sales Trend | Line Chart | Track monthly sales over time |
| Regional Performance | Map | Visualize sales and profit by state/region |
| Category Profitability | Bar Chart | Compare profit across categories and sub-categories |
| Customer Segment | Highlight Table | Compare Sales, Profit, AOV by segment |
| Shipping Performance | Stacked Bar Chart | Analyze shipping mode and delivery delay impact |
| Discount vs Profit | Scatter Plot | Show relationship between discount and profit |
| Return Analysis | Highlight Table | Identify return rates by category, region, segment |

**KPI Cards (Dashboard):**
- Total Sales: ₹217M
- Total Profit: ₹33M
- Return Rate: 4.55%

---

## 6. Filters and Interactions Used

**Interactive Filters:**
- Sales Trend → Use as Filter (filters all charts by time period)
- Category Profitability → Use as Filter (filters by category)
- Regional Performance → Use as Filter (filters by region)

**Action Filter:**
- Shipping Performance → Dashboard Action Filter → filters all sheets on bar selection

---

## 7. Key Business Insights

- **Technology** category drives 84% of total profit — Copiers (₹7.3M) is the top sub-category
- **South region** leads with ₹64.7M in sales — highest among all four regions
- **Home Office** segment generates highest revenue at ₹74.5M
- **Discounts above 20%** consistently result in negative profit per order
- **Standard Class** shipping (58% of orders) has the highest delay rate at avg 4.71 days
- **Furniture** has the highest return rate at 7.67% — East region Home Office at 12.63%
- **Office Supplies** contributes high order volume but lowest profit margin

---

## 8. Dashboard Story Summary

The business is profitable at 15.35% overall margin, driven by Technology products and the South region. However, three critical risks require immediate action: excessive discounting eroding margins, high Furniture return rates (especially in East region), and Standard Class shipping delays affecting customer satisfaction. Key opportunities exist in expanding Technology inventory, replicating South region strategies in East and West, and creating Home Office product bundles to increase Average Order Value.

---

## 9. Assumptions and Limitations

**Assumptions:**
- `return_flag = 1` indicates a returned order; `0` indicates no return
- `delivery_days = 0` for Same Day orders is treated as valid (same-day fulfillment)
- Discount values represent proportional discounts (0.20 = 20%)
- State field geo-coded to India for regional map visualization
- Orders with negative profit are treated as valid loss-making transactions

**Limitations:**
- No customer lifetime value or repeat purchase data available
- No competitor benchmarking data for margin comparison
- Campaign channel ROI cannot be calculated without cost data
- Map visualization shows approximate state-level geography
- Dashboard reflects historical data only — no real-time updates

---

## 10. Screenshots Included

| File | Description |
|------|-------------|
| `screenshots/full_dashboard.png` | Complete executive dashboard view |
| `screenshots/sales_trend_view.png` | Monthly sales trend line chart |
| `screenshots/regional_performance_view.png` | India regional map view |
| `screenshots/category_profitability_view.png` | Category and sub-category bar chart |
| `screenshots/filter_interaction_view.png` | Dashboard with active filter interaction |
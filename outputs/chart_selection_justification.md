### Task 10: Explain Chart Selection

---

## 1. Sales Trend — Line Chart

**Question it answers:** How are total sales changing over time from December 2023 to September 2025?

**Why this chart type is appropriate:** Line chart is the most effective chart for showing continuous data over time. It clearly reveals trends, peaks, and troughs in monthly sales, making it easy for leadership to identify seasonal patterns and growth trajectory.

**Fields used:**
- X-axis: MONTH(Order Date)
- Y-axis: SUM(Sales)

**Design principle applied:** Minimal clutter — single line with no unnecessary gridlines or colors, keeping focus on the trend itself.

**Mistake avoided:** Avoided using a bar chart for time series, which would make it harder to see the trend direction and continuity.

---

## 2. Regional Performance — Map

**Question it answers:** Which regions and states are performing best in terms of sales and profit across India?

**Why this chart type is appropriate:** A geographic map provides instant spatial context — leadership can immediately see which regions dominate and which are underperforming without reading through tables. It is the most natural way to present regional data.

**Fields used:**
- Latitude/Longitude: State (geographic role)
- Color: AGG(Profit Margin)
- Size: SUM(Sales)
- Detail: Region, State

**Design principle applied:** Used color and size together — size shows sales volume, color shows profitability — giving two dimensions of information in one view.

**Mistake avoided:** Avoided using a simple bar chart for regional data which would lose the geographic context and make it harder to identify location-based patterns.

---

## 3. Category Profitability — Bar Chart

**Question it answers:** Which product categories and sub-categories drive the most profit for the business?

**Why this chart type is appropriate:** A horizontal bar chart is ideal for comparing profit across multiple categories and sub-categories simultaneously. The length of each bar makes it immediately clear which sub-categories are most and least profitable.

**Fields used:**
- X-axis: SUM(Profit)
- Y-axis: Category, Sub Category
- Color: SUM(Profit)

**Design principle applied:** Sorted bars from highest to lowest profit within each category — making it easy to rank performance at a glance.

**Mistake avoided:** Avoided using a pie chart which would be difficult to read with 13 sub-categories and would not clearly show the magnitude of difference between Technology and other categories.

---

## 4. Customer Segment — Highlight Table

**Question it answers:** How do Consumer, Corporate, and Home Office segments compare across Sales, Profit, and Average Order Value?

**Why this chart type is appropriate:** A highlight table (heat map) allows comparison of multiple measures across multiple segments simultaneously. Color intensity immediately draws attention to high and low performing cells, making cross-segment comparison fast and intuitive.

**Fields used:**
- Rows: Customer Segment
- Columns: Measure Names (Average Order Value, Profit, Sales)
- Color: Measure Values
- Label: Measure Values

**Design principle applied:** Used color gradient from green to orange to highlight performance differences — warmer colors indicate higher values, making the table self-explanatory.

**Mistake avoided:** Avoided using separate bar charts for each metric which would require leadership to look at three different charts instead of one unified view.

---

## 5. Shipping Performance — Stacked Bar Chart

**Question it answers:** How many orders does each shipping mode handle and what proportion experience delivery delays?

**Why this chart type is appropriate:** A stacked bar chart shows both the total order count per shipping mode AND the breakdown by delivery delay bucket (Fast, Standard, Delayed) in a single view. This allows leadership to compare shipping volume and delay risk simultaneously.

**Fields used:**
- X-axis: CNTD(Order Id)
- Y-axis: Ship Mode
- Color: Shipping Delay Bucket (Green = Fast, Orange = Standard, Red = Delayed)

**Design principle applied:** Used meaningful colors — Green for fast delivery, Orange for standard, Red for delayed — creating an intuitive traffic light system that requires no legend explanation.

**Mistake avoided:** Avoided using a pie chart which cannot show the breakdown within each shipping mode. Also avoided a simple count table which would not visually highlight the delay proportion.

---

## 6. Discount vs Profit — Scatter Plot

**Question it answers:** What is the relationship between discount levels and profit? Does higher discount lead to lower profit?

**Why this chart type is appropriate:** A scatter plot is the only chart type that can effectively show the relationship (correlation) between two continuous numerical variables. Each point represents an order, making it possible to see the overall pattern and identify outliers.

**Fields used:**
- X-axis: SUM(Discount)
- Y-axis: SUM(Profit)
- Color: SUM(Profit) — green for positive, red for negative
- Detail: Order Id

**Design principle applied:** Used color to distinguish profitable (green) vs loss-making (red) orders, instantly highlighting the danger zone of high discounts.

**Mistake avoided:** Avoided using a line chart or bar chart which cannot show the correlation between two measures at the order level. A bar chart of average profit by discount bracket would hide individual order-level patterns.

---

## 7. Return Analysis — Highlight Table

**Question it answers:** Which combination of Category, Region, and Customer Segment has the highest return rate?

**Why this chart type is appropriate:** A highlight table with a crosstab structure allows leadership to see return rates across all combinations of three dimensions (Category × Region × Customer Segment) in a single compact view. Color intensity immediately identifies high-risk areas.

**Fields used:**
- Rows: Category
- Columns: Region, Customer Segment
- Color: AGG(Return Rate)
- Label: AGG(Return Rate)

**Design principle applied:** Used red color for high return rates and green for low, creating an immediate visual alert system for risk areas without requiring leaders to read every number.

**Mistake avoided:** Avoided using separate bar charts for each category which would require three charts and make cross-dimensional comparison difficult. A single highlight table communicates the same information more efficiently.
### calculated fields 

1. **Profit Margin**
   * **Formula:** `SUM([profit]) / SUM([sales])`
   * **Business Explanation:** This metric evaluates net financial efficiency per currency unit of revenue generated. It allows leadership to isolate structural pricing risks and identify product categories or geographic regions where high gross revenues are being cannibalized by underlying operating expenses.

2. **Cost**
   * **Formula:** `[sales] - [profit]`
   * **Business Explanation:** This metric establishes the true floor price of inventory by calculating the combined procurement, manufacturing, and upstream logistics overheads. It provides the financial baseline required to formulate sustainable minimum viable pricing strategies.

3. **Average Order Value**
   * **Formula:** `SUM([sales]) / COUNTD([order_id])`
   * **Business Explanation:** This metric tracks average customer wallet share and transactional basket size. It validates the effectiveness of upselling, cross-selling, and product bundling campaigns by measuring the average monetary value spent per unique transaction.

4. **Return Rate**
   * **Formula:** `SUM([return_flag]) / COUNT([order_id])`
   * **Business Explanation:** This metric quantifies supply chain friction, product rejection frequency, and reverse-logistics liability. It serves as a core quality assurance benchmark to flag potential catalog misrepresentations or inventory defects.

5. **Shipping Delay Bucket**
   * **Formula:**
     ```tableau
     IF [delivery_days] <= 2 THEN "Fast Delivery (0-2 Days)"
     ELSEIF [delivery_days] <= 4 THEN "Standard Delivery (3-4 Days)"
     ELSE "Delayed Delivery (5+ Days)"
     END
     ```
   * **Business Explanation:** This metric tiers operational fulfillment duration into actionable service level agreement (SLA) performance segments. It allows executives to audit carrier efficiency and correlate logistical delays directly with post-purchase customer satisfaction metrics.





   ### Task 8: Write Business Insights


## Insight 1: Complete Business Overview (All Areas)

**Observation:** The executive dashboard reveals a comprehensive picture of the retail business across all key performance areas.

**Data Evidence:**
- **Sales Trend:** Total sales ₹217,017,652 with seasonal peaks in March 2024 and August 2025
- **Regional Performance:** South leads with ₹64.7M sales, East is lowest at ₹48.9M
- **Category Profitability:** Technology dominates with ₹27.9M profit vs Furniture ₹3.6M
- **Customer Segment:** Home Office highest sales ₹74.5M, all segments have ~15% profit margin
- **Discount Impact:** Orders with 30%+ discount frequently generate negative profit
- **Shipping Performance:** Standard Class (58% orders) has highest delays at avg 4.71 days
- **Return Pattern:** Furniture has highest return rate at 7.67%, Technology lowest at 3.03%
- **Business Risk:** East region Home Office Furniture returns at 12.63% — critical risk area

**Business Interpretation:** The business is profitable overall but faces risks from excessive discounting, high furniture returns, and delivery delays in Standard Class shipping. Technology is the star category while Furniture needs attention.

**Recommended Action:** Focus on Technology expansion, cap discounts at 20%, improve Standard Class delivery SLAs, and investigate Furniture return root causes in East region.

---

## Insight 2: Sales Trend Shows Seasonal Volatility

**Observation:** Sales trend shows significant fluctuations between December 2023 and September 2025, with peak sales reaching ₹10M+ in certain months and dropping to ₹6M in others.

**Data Evidence:** Total sales stand at ₹217,017,652 across 4,200 orders. Sharp peaks are observed around March 2024 and August 2025.

**Business Interpretation:** The business is heavily dependent on seasonal demand. Inconsistent sales suggest lack of steady revenue pipeline and over-reliance on peak periods.

**Recommended Action:** Introduce off-season promotional campaigns and loyalty programs to stabilize monthly revenue. Target low-performing months with targeted discounts on high-margin products.

---

## Insight 2: South Region Leads in Sales and Profit

**Observation:** South region outperforms all other regions in both sales and profitability.

**Data Evidence:**
- South: Sales ₹64,693,707 | Profit ₹9,987,912
- North: Sales ₹54,555,801 | Profit ₹8,314,884
- West: Sales ₹48,908,980 | Profit ₹7,404,073
- East: Sales ₹48,859,164 | Profit ₹7,599,443

**Business Interpretation:** South region has a stronger customer base and higher purchasing power. East and West regions are underperforming relative to their potential.

**Recommended Action:** Replicate South region's successful sales strategies in East and West regions. Investigate top-performing states in South (Telangana, Kerala) and expand presence there.

---

## Insight 3: Technology Category Drives Maximum Profit

**Observation:** Technology category generates significantly higher profit compared to Furniture and Office Supplies.

**Data Evidence:**
- Technology: Copiers ₹7,310,055 | Accessories ₹7,186,863 | Phones ₹7,097,291 | Machines ₹6,449,101
- Furniture: Total profit ~₹3,557,835
- Office Supplies: Total profit ~₹1,705,137

**Business Interpretation:** Technology products have superior profit margins. Furniture and Office Supplies contribute to volume but not profitability.

**Recommended Action:** Increase inventory and marketing investment in Technology products, especially Copiers and Accessories. Consider reducing shelf space for low-margin Office Supplies sub-categories like Paper and Labels.

---

## Insight 4: Home Office Segment Generates Highest Revenue

**Observation:** Home Office segment leads in total sales among all three customer segments.

**Data Evidence:**
- Home Office: Sales ₹74,500,746 | Profit ₹11,555,047 | AOV ₹51,522
- Consumer: Sales ₹71,886,173 | Profit ₹11,030,581 | AOV ₹53,053
- Corporate: Sales ₹70,630,733 | Profit ₹10,720,685 | AOV ₹50,487

**Business Interpretation:** Home Office customers make high-value purchases, likely driven by remote work trends. All three segments show similar profit margins (~15%), indicating balanced pricing strategy.

**Recommended Action:** Launch targeted Home Office product bundles to further increase AOV. Develop corporate loyalty programs to boost Corporate segment performance.

---

## Insight 5: High Discounts Are Eroding Profit

**Observation:** Scatter plot shows clear negative correlation — as discount increases beyond 20%, profit drops significantly and turns negative.

**Data Evidence:** Orders with 0% discount show highest profit (up to ₹140K per order). Orders with 30%+ discount frequently show negative profit (losses up to -₹20K).

**Business Interpretation:** Excessive discounting is destroying profit margins. The business is losing money on heavily discounted orders while gaining minimal volume benefit.

**Recommended Action:** Cap maximum discount at 20% across all categories. Implement discount approval workflow for orders above 15%. Review and eliminate blanket discount policies.

---

## Insight 6: Standard Class Shipping Causes Maximum Delays

**Observation:** Standard Class shipping mode has the highest number of delayed deliveries among all shipping modes.

**Data Evidence:**
- Standard Class: 2,435 orders | Avg delivery 4.71 days | Highest delayed (red) orders
- Second Class: 894 orders | Avg delivery 2.68 days
- First Class: 630 orders | Avg delivery 1.77 days
- Same Day: 241 orders | Avg delivery 0.40 days

**Business Interpretation:** Over 58% of orders use Standard Class shipping, creating delivery delays that may impact customer satisfaction and repeat purchases.

**Recommended Action:** Negotiate better SLAs with Standard Class logistics partners. Offer incentivized upgrades to First Class for high-value orders. Set delivery expectation alerts for Standard Class customers.

---

## Insight 7: Furniture Has Highest Return Rate

**Observation:** Furniture category shows significantly higher return rates compared to Technology and Office Supplies.

**Data Evidence:**
- Furniture: Return Rate 7.67%
- Office Supplies: Return Rate 3.65%
- Technology: Return Rate 3.03%
- Overall Return Rate: 4.55% (191 out of 4,200 orders)

**Business Interpretation:** High furniture return rate suggests product quality issues, mismatched customer expectations, or delivery damage. This directly impacts profitability and operational costs.

**Recommended Action:** Conduct customer surveys on returned furniture items. Improve product descriptions and images online. Implement better packaging for furniture delivery to reduce damage-related returns.

---

## Insight 8: East Region Home Office Has Critical Return Risk

**Observation:** Home Office customers in East region show the highest return rate for Furniture at 12.63%.

**Data Evidence:**
- Furniture, East, Home Office: 12.63% return rate
- Furniture, North, Consumer: 9.68% return rate
- Technology, North, Consumer: 1.00% return rate (lowest)

**Business Interpretation:** East region Home Office segment represents a high-risk customer group for Furniture returns. This could indicate product-market mismatch or logistics issues specific to East region.

**Recommended Action:** Launch a dedicated quality check program for Furniture orders in East region. Offer pre-purchase consultation to Home Office buyers. Consider region-specific return policy adjustments to reduce fraudulent returns.

---

## Calculated Fields Used

| Calculated Field | Formula | Purpose |
|-----------------|---------|---------|
| Profit Margin | Profit / Sales | Measures profitability efficiency |
| Cost | Sales - Profit | Determines cost of goods sold |
| Average Order Value | Sales / COUNTD(Order Id) | Measures revenue per transaction |
| Return Rate | SUM(Return Flag) / COUNT(Order Id) | Tracks return frequency |
| Shipping Delay Bucket | IF Delivery Days <= 2 THEN "Fast" ELSEIF Delivery Days <= 5 THEN "Standard" ELSE "Delayed" END | Categorizes delivery performance |
# Exploratory Data Analysis (EDA) Report
## Amazon Sales Performance
**Objective: Business Insights**


**Date:** 13 January 2026  
**Dataset:** Amazon India Sales Data  
**Reporting Period:** Weekly Progress Summary  


## 1. Data Cleaning and Preprocessing (Weekly Accomplishments)

During the initial phase of the project, a comprehensive data cleaning and restructuring process was conducted to establish a robust foundation for analysis. The following technical tasks were completed:

### Dataset Integrity
Performed a thorough audit and cleaning of the primary datasets to ensure consistency across multiple sources.

### Datatype Standardization
Converted relevant date columns across all tables into a unified `datetime` format to support aging analysis and time-series forecasting.

### Missing Value Management
* **Courier Status Identification:** Identified significant gaps in the `Courier Status` field.
* **Logic Development:** Developed a logic to cross-reference the `Status` column to populate missing logistics data.
* **Data Pruning:** Rows with an excessive ratio of missing values compared to available data were dropped to maintain statistical significance.

### Correction of Erroneous Entries
Identified and recorded Amount = 0 for logically inconsistent records where the `Quantity` was zero but an `Amount` was recorded.

### Categorical Standardization
Standardized the `Category` column by resolving inconsistencies in casing and spelling, ensuring accurate grouping.

### Structural Refinement
* Identified relations within the data to assign appropriate names to previously unnamed columns.
* Corrected "jumbled" data where values had shifted into incorrect columns across specific rows.
* Removed irrelevant and redundant columns that did not contribute to the analytical objectives.

### Feature Engineering and Integration
* Generated new calculated fields to derive more granular business insights.
* Integrated related data points from disparate tables, specifically merging `Colors` and `Stock` metrics from the Sales Report into the primary Amazon and International Sales datasets.

---

## 2. Key Findings and Insights

### A. High-Risk Product Identification
* **Observation:** While raw return counts are higher for top-selling items, the true operational risk is found in the Return-to-Sales Ratio.
* **Insight:** 16 High-Risk Styles were identified with return/cancellation rates exceeding 30%.
* **Financial Impact:** These specific styles contribute to a potential loss of approximately **₹348,500.00** every 90 days.
* **Recommendation:** Conduct an immediate quality audit on problematic SKUs, specifically focusing on styles `SET195` (41% return rate) and `JNE3608`.

### B. The "Zero Quantity" Issue
* **Observation:** A significant volume of cancelled orders is associated with a quantity of 0.
* **Insight:** These entries generate no revenue, increase system network traffic, and introduce operational noise into the reporting pipeline.
* **Recommendation:** Check for any bugs in the software that makes the quantity 0 for a valid, or if the app allows 0 quantity orders and remove it.

### C. Shipping Service Performance
* **Observation:** Cancellation rates fluctuate significantly based on the `ship-service-level`.
* **Insight:** Expedited Shipping correlates with lower cancellation rates, whereas Standard Shipping exhibits higher buyer drop-off rates.
* **Recommendation:** Expand Expedited Shipping coverage and optimize logistics infrastructure in high-volume states, specifically Maharashtra and Karnataka.

### D. Operational Backlog and At-Risk Revenue
* **Observation:** Pending and in-transit orders represent a substantial financial float.
* **Key Metrics:**
    * **Revenue at Risk:** Approximately ₹50.75 Million
    * **Delayed Orders:** 78,000+ entries
    * **Average Order Age:** 46.6 days
* **Insight:** Fulfillment delays significantly increase the statistical probability of cancellations and refunds.
* **Recommendation:** Increase delivery partner density in the top five states to reduce average order age and convert at-risk revenue into realized profit.
* Delivery partners need not be added for every order, we can look at previous trends and increase delivery partners only for that duration.

### E. The Surat Issue
* **Observation:** All the orders that had amount missing was from one PINCODE: 394210
* **Recommendations:** More investigation into the backend team is required to resolve the high frequency of missing `Amount` values.


## 3. Visualizations and Graphs Summary

| Analysis Type | Visualization Used | Key Takeaway |
| :--- | :--- | :--- |
| **Cancellations vs. Quantity** | Line Plot | Orders with Qty = 0 are the primary drivers of system noise. |
| **Return Rate Analysis** | Scatter Plot | Identifies styles in the “Danger Zone” (High Return % / Low volume). |
| **Category Distribution** | Donut / Pie Chart | “Set” and “Kurta” categories represent the bulk of the volume. |
| **Operations Flow** | Area / Trend Chart | Visualizes the persistent gap between incoming orders and backlog. |
| **Geographical Density** | Bar Chart | Surat (Pincode 394210) shows high volume but high error rates. |


## 4. Final Strategic Recommendations

### A. Inventory Optimization
* Immediately review the top 10 loss-making styles for fabric quality and sizing inconsistencies.
* Delist SKUs if performance metrics do not improve within the next review cycle.

### B. Logistics Strategy
* Prioritize investment in Expedited Shipping infrastructure within high-volume regions to mitigate buyer remorse and delivery delays.

### C. Data Quality and Systems Audit
* Investigate the data logging failures at the Surat (Pincode 394210) regional hub to resolve the high frequency of missing "Amount" values.

### D. Customer Segmentation
* With 99.5% of the order volume originating from B2C channels, focus technical and marketing resources on retail customer user experience and delivery speed rather than B2B features.

---

## Conclusion
The data cleaning and preprocessing phase completed this week has provided a reliable dataset for high-level decision-making. The resulting EDA highlights critical revenue leakages and logistics inefficiencies. Addressing these systemic risks can potentially recover millions in revenue while significantly improving operational throughput.

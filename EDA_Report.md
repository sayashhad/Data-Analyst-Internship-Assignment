# **Exploratory Data Analysis (EDA) Report**
## **Amazon Sales Performance**

---

**Date:** *January 2026*  
**Dataset:** *Amazon India Sales Data*

---

## **1. Key Findings and Insights**

---

### **A. The “Zero Quantity” Issue**

**🔍 Observation:**  
A **significant volume of cancelled orders** are associated with a **quantity of `0`**.

**💡 Insight:**  
Products with **zero quantity**:
- Generate **no revenue**
- Increase **network traffic**
- Add **operational noise** to the platform

**✅ Actionable Recommendation:**  
**Remove the “Zero Quantity” option** from the web interface to ensure only **valid, revenue-generating orders** are processed.

---

### **B. High-Risk Product Identification (Returns vs. Sales)**

**Observation:**  
- Raw return counts are **highest for top-selling items**
- True risk emerges when analyzing the **Return-to-Sales Ratio**

**Insight:**  
- **16 High-Risk Styles** identified  
- Each has a **return/cancellation rate exceeding 30%**

**Financial Impact:**  
> These styles alone contribute to a **potential loss of ₹38,320.47 every 90 days**

**Actionable Recommendation:**  
- **Discontinue or audit** problematic SKUs  
- Prioritize investigation of:
  - **SET195** → *41% return rate*
  - **JNE3608**

---

### **C. Shipping Service Performance**

**Observation:**  
Cancellation rates vary significantly based on **ship-service-level**.

**Insight:**  
- **Expedited Shipping** → *Lower cancellation rates*  
- **Standard Shipping** → *Higher buyer drop-offs*

**Actionable Recommendation:**  
- Expand **Expedited Shipping coverage**
- Optimize logistics in **high-volume states**:
  - *Maharashtra*
  - *Karnataka*


---

### **D. Operational Backlog & “At-Risk” Revenue**

**Observation:**  
Pending and in-transit orders represent a **large financial float**.

**Key Metrics:**
- **Revenue at Risk:** ~₹**50.75 Million**
- **Delayed Orders:** **78,000+**
- **Average Order Age:** **46.6 days**

**Insight:**  
Delays significantly increase the likelihood of **cancellations and refunds**.

**Actionable Recommendation:**  
- Increase **delivery partner density** in the **top 5 states**
- Reduce average order age to convert:
  - *At-risk revenue* → **realized profit**

---

## **2. Visualizations and Graphs**

| **Analysis Type** | **Visualization Used** | **Key Takeaway** |
|------------------|------------------------|------------------|
| Cancellations vs. Quantity | Line Plot | Orders with **Qty = 0** are the primary drivers of cancellations |
| Return Rate Analysis | Scatter Plot | Highlights styles in the **“Danger Zone”** (High Return % / Low–Mid Volume) |
| Category Distribution | Donut / Pie Chart | **Set** and **Kurta** categories dominate volume |
| Operations Flow | Area / Trend Chart | Visualizes the **gap between incoming orders and backlog** |
| Geographical Density | Bar Chart | **Surat (Pincode 394210)** shows high volume with high error rates |

---

## **3. Final Strategic Recommendations**

### **A Inventory Pruning**
- Immediately review **top 10 loss-making styles**
- Focus areas:
  - Fabric quality
  - Sizing inconsistencies
- **Delist** SKUs if no improvement is observed  
  *(e.g., SET195, JNE3608)*

---

### **B. Logistics Investment**
- Expand **Expedited Shipping infrastructure**
- Prioritize **high-volume states**
- Objective:
  - Reduce delivery delays
  - Lower cancellation rates

---

### **C. Data Quality Audit**
- Investigate **Pincode 394210 (Surat)**
- Issue identified:
  - High frequency of **missing “Amount” values**
- Likely cause:
  - Regional system logging failure or integration bug

---

### **D. Customer-Centric Strategy**
- **99.5% of orders are B2C**
- Focus efforts on:
  - Retail customer UX
  - Personalization
  - Faster delivery commitments
- Avoid over-investing in **B2B-specific features**

---

### **Conclusion**
This EDA highlights **critical revenue leakages**, **logistics inefficiencies**, and **inventory risks**. Addressing these areas can unlock **millions in recovered revenue** while improving **customer satisfaction and operational efficiency**.

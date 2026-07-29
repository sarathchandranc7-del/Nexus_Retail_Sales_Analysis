# Nexus Retail Group: E-Commerce Analytics & Operations Dashboard
A Power BI project analyzing e-commerce revenue and supply chain efficiency for Nexus Retail Group.

About the Project
This project involves the design and development of an end-to-end business intelligence dashboard for Nexus Retail Group, a simulated large-scale e-commerce enterprise. The primary objective of this analysis is to separate commercial sales performance from operational fulfillment, providing executives with a clear, segmented view of the business. 

## Tools & Methodologies Demonstrated
*   **Data Cleaning & Preprocessing:** Microsoft Excel (Power Query, Data Validation)
*   **Data Modeling:** Power BI (Star Schema design, 1-to-Many relationships)
*   **Calculations:** Advanced DAX (Time Intelligence, Iterators, CALCULATE functions)
*   **Data Visualization:** Custom UI/UX design, conditional formatting, dynamic filtering via slicers
*   **Domain Focus:** E-commerce commercial performance and supply chain logistics

The application is structured into four distinct analytical areas:
*   **Home/Navigation:** A clean, executive portal for report navigation.
*   **Sales Performance:** Tracking revenue generation and profitability.
*   **Customer Report:** Analyzing demographics and regional buyer behavior.
*   **Order & Shipping Analysis:** Tracking supply chain efficiency, delivery bottlenecks, and return trends.
*   **Summary:** major changes and key points in the analysis
## 2. Data Collection
The dataset consists of 4,200 transactional records encompassing the entire customer journey from purchase to delivery. The data includes dimensions such as Customer Demographics (Age, Gender, Location), Transactional Data (Order ID, Payment Method, Unit Price, Discount), and Fulfillment Data (Order Status, Days to Ship, Return Flag, Customer Satisfaction).

## 3. Phase 1: Preprocessing in Excel
Before importing into Power BI, the raw data underwent rigorous cleaning and structuring in Excel. 
*   **Structural Changes:** The file was organized into distinct sheets (`Raw`, `Cleaned Data`, and an audit trail `Changes made` log) to maintain data integrity.
*   **Data Quality:** Handled missing values, standardized the `Order Status` and `Payment Method` text formats, and ensured that numerical columns like `Sales Amount` and `Profit` were formatted as decimals for seamless DAX aggregation.
*   **Challenges:** A key challenge was ensuring the date fields and the calculated `Days to Ship` column were perfectly formatted as whole numbers, as any text strings mixed into these columns would break the time-intelligence calculations in Power BI.

## 4. Phase 2: Power BI Dashboard
The dashboard was built with a custom UI/UX design utilizing a deep teal and golden yellow corporate color palette. 

**Key DAX Measures Performed:**
*   **Average Shipping Time:** `AVERAGE('Cleaned Data'[Days to Ship])` - Crucial for evaluating supply chain speeds.
*   **Total Orders:** `DISTINCTCOUNT('Cleaned Data'[Order ID])` - Used to calculate the exact volume of fulfillment required.
*   **Profit Margin %:** `DIVIDE(SUM('Cleaned Data'[Profit]), SUM('Cleaned Data'[Sales Amount]), 0)`

![image](images/Csutomer_report.JPG)


## 5. Findings & Strategic Insights
Based on the analysis, several key operational and commercial insights were uncovered:

1.  **Financial Health:** The business generated $231.7 million in total sales while maintaining a strong profit margin of 21.36%.
2.  **Purchasing Behavior:** Customers are driving significant revenue per transaction, with the Average Order Value (AOV) sitting at an impressive $55,170.
3.  **Product Dominance:** Out of all product lines, the Electronics category stands out as the most dominant revenue driver.
4.  **Geographic Demand:** The South region leads the market as the highest revenue-generating geographic area, presenting opportunities for localized marketing.
5.  **Logistics Efficiency:** The supply chain currently fulfills customer orders with an average shipping time of 5.51 days. 
6.  **Quality Control:** Post-purchase metrics reveal a 14.57% return rate and a moderate average customer satisfaction score of 3.10 out of 5. 

**Suggestions:**
Given the 5.51-day average shipping time and the 14.57% return rate, there is a clear opportunity to optimize the fulfillment center workflow. Reducing transit times could directly improve the moderate 3.10 CSAT score and lower the volume of returned merchandise.

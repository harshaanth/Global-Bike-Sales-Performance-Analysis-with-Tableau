# **Tableau Sales Analysis Project**

## **Project Title:**  
**Global Bike Sales Performance Analysis**

## **Project Description:**  
This project aims to analyze sales performance trends using the **GBI_Large_DataSet_Dollar** dataset. The analysis covers multiple business intelligence aspects, including revenue trends, units sold, net profit, and discount analysis across different sales organizations, material groups, and bike models. The project addresses specific business questions through step-by-step Tableau visualizations, utilizing calculated fields, reference lines, bar charts, spark lines, and scatter plots to gain insights into the data.

## **Business Questions Addressed:**  
1. **What is the overall average revenue, and what is the average revenue for Bike Studio Berlin?**
2. **Were the number of units ordered in 2007 greater than the number of units ordered in 2006 across all material groups and bike models?**
3. **Which bike had the highest net profit, and did it change from 2006 to 2007?**
4. **Which bike had the highest average discount?**
5. **What is the correlation between revenue and cost of goods sold, and between revenue and sales quantity?**

## **Project Files:**  
- **Data Set:** `GBI_Large_DataSet_Dollar.xlsx` (Main data used for analysis)
- **Tableau Workbook:** `Bike_Sales_Analysis.twbx` (Includes all visualizations and calculated fields)
- **ReadMe File:** `README.md` (This documentation file)
- **PowerPoint Presentation:** `Bike_Sales_Analysis.pptx` (Contains all visualizations exported from Tableau)

## **Steps Breakdown:**  

### **Part A - Visualization 1: Average Revenue Analysis**  
**Business Question:**  
What is the overall average revenue? What is the average revenue for Bike Studio Berlin?

**Steps:**  
1. **Open Data Set in Tableau:** Load `GBI_Large_DataSet_Dollar.xlsx` in Tableau.
2. **Sheet 1 Setup:**  
   - Drag `Sales Org` and `MatGroup Text` to **Columns**.
   - Drag `Revenue` to **Rows**.
   - Change aggregation to `SUM(Revenue)`.
   - Rotate the bar chart vertically and sort by `SUM(Revenue)` in descending order.
3. **Adding Reference Lines:**  
   - Switch to the **Analytics Pane** and drag a **Reference Line** onto the chart for the overall average revenue.
   - Add a second reference line for each sales organization (pane) with the average revenue for each.
   - Format reference lines to differentiate between the overall average and sales org-specific average (e.g., change colors and line types).
4. **Results:**  
   - The **Overall Average Revenue** is **$4,929,476**.
   - The **Average Revenue for Bike Studio Berlin** is **$4,924,973**.

### **Part B - Visualization 2: Units Sold Comparison (2006 vs 2007)**  
**Business Question:**  
Were the number of units ordered in 2007 greater than in 2006 across all material groups and bike models?

**Steps:**  
1. **Create Calculated Fields:**  
   - `Units Sold in 2006`:  
     `IF YEAR([Date]) = 2006 THEN [Sales Quantity] END`
   - `Units Sold in 2007`:  
     `IF YEAR([Date]) = 2007 THEN [Sales Quantity] END`
2. **Create Bar Chart:**  
   - Drag `Sales Org` and `MatGroup Text` to **Rows**.
   - Drag `Units Sold in 2006` and `Units Sold in 2007` to **Columns**.
   - Combine both years into one chart by dragging `Units Sold in 2007` onto the x-axis of `Units Sold in 2006`.
3. **Format the Bar Chart:**  
   - Drag `Measure Names` to **Colors** and **Size** to stack the bars and distinguish between years.
4. **Analysis Results:**  
   - Confirmed that **2007 sales were greater** than 2006 in all material groups.
   - An exception: **Disney bike model from Munich** sold **713 units in 2006** and **700 in 2007**.

### **Part C - Visualization 3: Sparkline for Revenue Trends**  
**Business Question:**  
What are the monthly revenue trends for each bike?

**Steps:**  
1. **Create Sparkline:**  
   - Drag `Materials` to **Rows** and `Revenue` to **Rows** next to it.
   - Drag `Date` to **Columns** and change it to continuous months.
2. **Adjust Axes:**  
   - Ensure independent axis ranges for each row.
   - Remove x and y-axis headers for a cleaner look.
3. **Additional Sparkline Analysis:**  
   - Create another sparkline to display trends for all measures by using `Measure Names` and `Measure Values`.
4. **Analysis Results:**  
   - Revenue spikes during summer months, confirming increased bike sales in warmer months.

### **Part D - Visualization 4: Net Profit Analysis**  
**Business Question:**  
Which bike had the highest net profit, and did it change from 2006 to 2007?

**Steps:**  
1. **Create Calculated Field for Net Profit:**  
   - `Net Profit = [Revenue] - [Discount] - [Cost of Goods Sold]`
2. **Create Bar Chart for Net Profit:**  
   - Drag `Materials` to **Rows** and `Net Profit` to **Columns**.
   - Sort the bar chart to show bikes with the highest net profit.
3. **Year Comparison:**  
   - Add `Year(Date)` to color the bars by year for comparison.
4. **Analysis Results:**  
   - **AC DS 1** had the highest net profit of **$1,633,299**.
   - Net profit increased from 2006 to 2007.

### **Part E - Visualization 5: Discount and Revenue Correlation**  
**Business Question:**  
Which bike had the highest discount, and how does discount correlate with revenue?

**Steps:**  
1. **Average Discount Analysis:**  
   - Create a bar chart by dragging `Materials` to **Rows** and `Discount` to **Columns**.
   - Change aggregation to average and sort by the highest discounts.
2. **Scatter Plot for Correlation:**  
   - Create scatter plots to compare:
     - **Revenue vs Discount**
     - **Revenue vs Cost of Goods Sold**
     - **Revenue vs Sales Quantity**
   - Add a trendline to analyze the correlation.
3. **Analysis Results:**  
   - Strong correlation between **Revenue and Cost of Goods Sold** with an **R-squared of 0.997**.
   - Weaker correlation between **Revenue and Sales Quantity**.

## **Conclusion:**  
This Tableau project provides a comprehensive analysis of bike sales performance across multiple dimensions. The visualizations and calculated fields created in this project address key business questions, offering insights into sales trends, net profit, discounts, and performance comparisons across different years.

## **Repository Structure:**  
- **Data Set:** `GBI_Large_DataSet_Dollar.xlsx`
- **Tableau Workbook:** `Bike_Sales_Analysis.twbx`
- **ReadMe File:** `README.md`
- **PowerPoint Presentation:** `Bike_Sales_Analysis.pptx` (Contains all visualizations exported from Tableau)

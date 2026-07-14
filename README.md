
## Documentation


# E-Commerce-Dashboard


## Problem Statement

This dashboard helps an e-commerce/retail business (operating across Gbagada, Ibadan, Ikoyi, Lekki, and Surulere) understand its sales performance, product performance, and customer base. It helps the business know which branches, products, and customer segments are driving revenue and profit, so that underperforming areas can be identified and improved.

Across the covered order period (5/18/2018 – 7/21/2021), the business recorded **Ksh29,358,677** in total sales, **Ksh17,277,794** in product cost, and **Ksh12,080,884** in profit from **27,659 orders**.

Ibadan alone contributed **Ksh15.7M in sales** and **Ksh6.46M in profit** — by far the largest branch — while Gbagada, the smallest branch, generated just **Ksh1.25M in sales**. This kind of gap signals where the business should focus expansion or investigate underperformance.

Also, since Bikes account for **95.24%** of profit versus **3.63%** for Accessories, the product mix is heavily concentrated in one category, which the dashboard highlights as a possible diversification opportunity.

### Steps followed

- **Step 1** : Load the sales, product, and customer data into Power BI Desktop.
- **Step 2** : In Power Query Editor, under the View tab, check "Column distribution", "Column quality", and "Column profile" (set to "Column profiling based on entire dataset") to review data quality across Order Date, Branch, Product, and Customer tables.
- **Step 3** : Build a data model linking Sales/Orders to Product, Customer, and Branch dimension tables.
- **Step 4** : Create a **Profit** measure as Total Sales minus Product Cost:

      Profit = SUM(Sales[TotalSales]) - SUM(Sales[TotalCost])

- **Step 5** : Create a **Total Orders** measure to count distinct orders:

      Total Orders = DISTINCTCOUNT(Sales[OrderID])

- **Step 6** : Create a **Total Customers** measure to count unique customers:

      Total Customers = DISTINCTCOUNT(Customer[CustomerID])

- **Step 7** : In the report view, add a Year and Month slicer (visible on the Product and Customer dashboard pages) so users can filter all visuals by order date.
- **Step 8** : Build the **Sales Summary** page with a header image/background, and three card visuals for Total Sales, Product Cost, and Total Profit, plus a date range slider (5/18/2018 – 7/21/2021).
- **Step 9** : Build the **Sales Dashboard** page:
  - Three KPI cards comparing Total Sales, Product Cost, and Profit vs. last year.
  - A **Sales by Branch** table (Branch, Total Order, Total Sales, Total Cost, Profit) with a Total row.
  - A horizontal bar chart for **Profit by Product**.
  - Donut charts for **Profit by Gender** and **Profit by Category**.
  - A dynamic narrative/insight text box (Power BI's smart narrative visual) summarizing the top and bottom performing products.
- **Step 10** : Build the **Product Dashboard** page:
  - Card visuals for total Product count (397) and total Orders (27,659).
  - A callout for the Top Product by Profit ("All-Purpose Bike Stand").
  - Bar charts for **Top 10 Product (Sales)**, **Top 10 Product (Profit)**, and **10 Least Performing Product**.
  - A detail table listing ProductName, Profit, and EP (Extended Price) per product.
  - A **Top 3 Branches** bar chart (Ibadan, Surulere, Lekki) by profit.
- **Step 11** : Build the **Customer Dashboard** page:
  - A customer-level table (Name, Total Order, Total Sales).
  - Donut charts for **Total Order by Gender**, **Total Order by Occupation**, and **Total Order by MaritalStatus**.
  - Card visuals for Total Customers (18,484), Total Orders (27,659), and Top Customer by Sales ("Jordan Turner").
  - A column chart for **Total Order by Month**, arranged from December through January.
- **Step 12** : Add a consistent navigation bar (Sales summary, Sales dashboard, Product Dashboard, Customer Dashboard) across all pages using bookmarks/buttons so users can move between pages.
- **Step 13** : Apply a consistent theme (dark navy header, light blue KPI cards) across all four pages for visual consistency.
- **Step 14** : Publish the report to Power BI Service.

> **Note:** DAX expressions above are illustrative of the underlying logic based on the visuals shown (Sales − Cost = Profit, distinct order/customer counts, etc.). Replace them with your actual measure definitions from the .pbix file for full accuracy.

# Snapshots of Dashboard

<img width="1300" height="729" alt="Image" src="https://github.com/user-attachments/assets/19043997-63f1-4cd0-a454-0942c894c2ac" />


<img width="1292" height="747" alt="Image" src="https://github.com/user-attachments/assets/485cec7e-eaf1-46f2-976a-39689b9c5bbc" />

<img width="1297" height="737" alt="Image" src="https://github.com/user-attachments/assets/bb8f89bd-6cb1-4280-ba96-5e0437b10e52" />


<img width="1296" height="744" alt="Image" src="https://github.com/user-attachments/assets/59939e70-7739-40e4-89f3-d6dce8a3a85e" />

# Insights

A four-page report was created in Power BI Desktop covering Sales Summary, Sales, Product, and Customer performance.

Following inferences can be drawn from the dashboard:

### [1] Overall Performance

- Total Sales = **Ksh29,358,677.22**
- Total Product Cost = **Ksh17,277,793.58**
- Total Profit = **Ksh12,080,884**
- Total Orders = **27,659**
- Total Customers = **18,484**

### [2] Sales by Branch

| Branch | Total Order | Total Sales | Total Cost | Profit |
|---|---|---|---|---|
| Gbagada | 1,471 | Ksh1,249,233.16 | Ksh736,209.60 | Ksh513,024 |
| Ibadan | 11,215 | Ksh15,736,656.54 | Ksh9,277,043.72 | Ksh6,459,613 |
| Ikoyi | 4,283 | Ksh3,311,377.95 | Ksh1,944,748.27 | Ksh1,366,630 |
| Lekki | 4,751 | Ksh3,710,242.17 | Ksh2,177,130.81 | Ksh1,533,111 |
| Surulere | 5,978 | Ksh5,351,167.40 | Ksh3,142,661.17 | Ksh2,208,506 |
| **Total** | **27,659** | **Ksh29,358,677.22** | **Ksh17,277,793.58** | **Ksh12,080,884** |

Thus, **Ibadan** is the dominant branch, contributing roughly **54%** of total profit, while **Gbagada** is the weakest performer.

### [3] Product Performance

- Total distinct products = **397**
- Top product by profit = **All-Purpose Bike Stand** (Ksh24,784 profit)
- Highest-profit individual bike SKU = **Mountain-200 Black, 46** at **Ksh626,621.57**, which was **318.36%** higher than the lowest-profit SKU, **Road-250 Red, 48**, at **Ksh149,779.30**.
- The 10 least-performing products each generated only around **Ksh3,375–Ksh3,578** in profit — a fraction of the top performers.

### [4] Profit by Category & Gender

- **Bikes**: 95.24% of profit
- **Accessories**: 3.63% of profit

       thus, the product portfolio is heavily bike-dependent, with accessories/clothing contributing marginally.

- **Male** customers: 49.52% of profit
- **Female** customers: 50.48% of profit

       thus, profit is almost evenly split by gender, with a slight lean toward female customers.

### [5] Customer Demographics

**Total Order by Gender**
- Male: 50.32%
- Female: 49.68%

       thus, order volume is nearly balanced by gender.

**Total Order by Occupation**
- Professional: 31.31%
- Skilled Manual: 23.86%
- Management: 17.42%
- Clerical: 15.9%
- Manual: 11.5%

       thus, Professional and Skilled Manual customers place the most orders.

**Total Order by Marital Status**
- Married: 54.8%
- Single: 45.2%

       thus, married customers account for the majority of orders.

### [6] Seasonality — Total Order by Month

| Month | Orders |
|---|---|
| Dec | 2,661 |
| Nov | 2,072 |
| Oct | 2,070 |
| Sep | 1,951 |
| Aug | 2,011 |
| Jul | 1,888 |
| Jun | 2,730 |
| May | 2,755 |
| Apr | 2,536 |
| Mar | 2,405 |
| Feb | 2,298 |
| Jan | 2,282 |

Order volume peaks in **May and June**, dips to its lowest in **July**, and rises again toward **December**, suggesting a mid-year and year-end seasonal demand pattern.

### [7] Top Customer

- **Jordan Turner** is the top customer by total sales value.

Sales Dashboard 2026 (Power BI Mini Project)
An interactive Power BI sales dashboard built from two CSV tables (customers and orders). The project covers the Power BI workflow end to end: data import, cleaning in Power Query, data modeling, DAX calculations and visuals.

Business Questions
- How do sales change over time, by year and quarter?
- Which products and product categories bring in the most sales and units?
- How do results change by country, product category and date range?
- 
Tools Used
- Power BI Desktop
- nPower Query (data cleaning and transformation)
- DAX (calculated column and custom logic)
- 
Data
Two CSV files, stored in the data/ folder:
- customers.csv: 12 customers with ID, name, country, state, city and score
- orders.csv: 100 orders with order ID, customer ID, order date, product name, product category, quantity and sales
  
Steps I Followed

1. Import: Loaded both CSV files into Power BI.
2. Power Query: Promoted headers, set data types and merged first_name and last_name into a single customer_name column (concatenation).
3. Date formatting: Set the order_date column to a date format in Table view.
4. Data cleaning with DAX: The score field in the customers file was blank for 4 of 12 customers (C003, C006, C008, C011). I created a calculated column, Clean Score, that treats blanks as 0 using COALESCE, so calculations on the score work without errors. The original score column is unchanged.
5. Data model: Created a one-to-many relationship from customers[customer_id] to orders[customer_id].
6. Visuals: Built an interactive dashboard (see below).

DAX

Clean Score = COALESCE(customers[score], 0)

Dashboard Features

- KPI cards: total orders, total customers, total sales
- Line chart: sales by year and quarter
- Bar chart: total sales by product
- Donut chart: sales share by product category
- Funnel chart: quantity sold by product category
- Slicers: date range, country and product category
  
Dashboard Preview:

Data Model:
Key Insights

- Total sales of about 103K across 100 orders from 12 customers.
- Laptops are the top category at about 52K, roughly half of all sales. Dell XPS 15 is the top product at about 25K.
- Laptops (37 units) and smartphones (32 units) lead by quantity sold.
- Sales trend upward, with a sharp rise toward mid-2026.
  
Files in This Repo
Sales Dashboard (2026).pbix: the Power BI file (open with Power BI Desktop)
data/: source CSV files
images/: dashboard and data model screenshots

Author
Arul Vetrivelan | Data Analyst (SQL, Power BI, Excel)

E-commerce Sales Analysis Dashboard
This repository contains the complete project for an E-commerce Sales Analysis dashboard built with SQL and Power BI. The project analyzes sales data from multiple sources to provide key insights into product performance, customer behavior, and overall business health.

📊 Dashboard Preview
The interactive dashboard provides a multi-faceted view of the sales data. It is composed of three main reports: a general dashboard, a product-focused report, and a customer-focused report.

(To make this image work, upload the screenshot to your repository and update the link above.)

✨ Key Features & Insights
📈 Main Dashboard
KPIs: Tracks high-level metrics including Total Sales (4bn), Total Orders (52K), Total Stock (59K), and Average Rating (2.88).

Sales by Category: Visualizes the top-performing product categories, with Stationery and Toys leading.

Monthly Order Trends: A line chart showing the distribution of orders throughout the year.

Order Status: A donut chart breaking down orders by their status (Delivered, Returned, Cancelled).

Sales by Zone: A pie chart illustrating the sales distribution across different geographical zones (North, South, East, West).

📦 Product Report
Top Products: A detailed table of the best-selling products by units sold and total revenue.

Stock by Category: A bar chart showing the inventory levels for each product category.

Daily Order Trends: A line chart analyzing order patterns across the days of the week, with a peak on Saturday.

👥 Customer Report
Customer KPIs: Tracks key customer metrics like Total Customers (4.7K) and Total Reviews (47K).

Orders by Customer Age: A line chart showing the purchasing frequency across different age groups.

Customer Demographics: Visualizations for customer distribution by Gender and State.

⚙️ Project Workflow
Data Collection: Sourced raw data from three separate CSV files: customer_data.csv, orders_data.csv, and product_data.csv.

Data Extraction & Transformation: Used SQL to query the data, perform joins, and aggregate key metrics.

Data Modeling: Loaded the data into Power BI to create a relational model.

DAX Calculations: Developed DAX measures in Power BI to calculate complex KPIs.

Dashboard Development: Designed and built an interactive, multi-page dashboard in Power BI to visualize the insights.

🛠️ Tools and Technology Used
Microsoft Excel: Used for handling the initial CSV data files.

SQL: The primary language used for querying and aggregating the data from the source files.

Power BI: The core tool for data modeling, DAX measure creation, and building the final interactive dashboard.

Power Query: Used within Power BI for data cleaning and transformation (ETL).

📝 SQL Queries
Below are some of the key SQL queries used to extract and aggregate the data for the dashboard.

Total Sales by Category
SELECT
    p.category,
    SUM(o.order_quantity * p.price) AS Total_Sales
FROM
    orders AS o
JOIN
    products AS p ON o.product_id = p.product_id
GROUP BY
    p.category
ORDER BY
    Total_Sales DESC;

Total Sales by Zone
SELECT
    c.zone,
    SUM(o.order_quantity * p.price) AS Total_Sales
FROM
    customers AS c
JOIN
    orders AS o ON c.customer_id = o.customer_id
JOIN
    products AS p ON o.product_id = p.product_id
GROUP BY
    c.zone;

Top 10 Products by Revenue
SELECT
    p.name,
    SUM(o.order_quantity) AS Total_Orders,
    SUM(o.order_quantity * p.price) AS Total_Revenue
FROM
    products AS p
JOIN
    orders AS o ON o.product_id = p.product_id
GROUP BY
    p.name
ORDER BY
    Total_Revenue DESC
LIMIT 10;

🚀 Getting Started
To explore this project, you will need to have Power BI Desktop installed.

Clone the repository:

git clone [https://github.com/YOUR_USERNAME/YOUR_REPOSITORY.git](https://github.com/YOUR_USERNAME/YOUR_REPOSITORY.git)

Open the Power BI file: Navigate to the project directory and open the .pbix file.

Data Source: The project uses the included CSV files (customer_data.csv, orders_data.csv, product_data.csv) as its data source.

📞 Contact
Your Name - [Your Email Address] - [Link to your LinkedIn profile]

Project Link: https://github.com/YOUR_USERNAME/YOUR_REPOSITORY

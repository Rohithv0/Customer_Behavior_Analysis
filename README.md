# Customer_Behavior_Analysis
Analyzed 3,900 customer transactions using Python, SQL, and Power BI to uncover spending patterns, product preferences, customer segments, and subscription behavior insights.

🛍️ Customer Shopping Behavior Analysis
A complete end-to-end data analytics project that explores customer purchasing patterns through Python-based EDA, SQL querying, and interactive Power BI dashboards — presented with a Gamma-powered report and slide deck.

📌 Overview
This project analyzes a retail customer shopping dataset to uncover trends in purchase behavior, category preferences, discount usage, and demographic patterns. The goal is to transform raw data into actionable business insights using a full analytics pipeline — from data cleaning to executive-ready dashboards.
Key Business Questions Answered:

Which customer age groups spend the most?
Which product categories generate the highest revenue?
How does discount/promo usage affect purchase frequency?
What are the most popular payment and shipping methods?


📂 Dataset
PropertyDetailsFilecustomer_shopping_behavior.csvSourceRetail customer transaction recordsRecords~3,900 rowsKey ColumnsCustomer ID, Age, Gender, Category, Purchase Amount (USD), Review Rating, Frequency of Purchases, Discount Applied, Promo Code Used, Payment Method, Shipping Type

🛠️ Tools & Technologies
LayerToolLanguagePython 3.xData ManipulationPandasDatabasePostgreSQL (via pgAdmin 4)DB ConnectorSQLAlchemy, psycopg2BI DashboardMicrosoft Power BIReportGamma (AI-powered report)PresentationGamma (AI-powered slides)NotebookJupyter Notebook

🔢 Project Steps
1. 📥 Load Data

Imported the CSV dataset into a Pandas DataFrame
Previewed structure using .head(), .info(), and .describe()

2. 🔍 Exploratory Data Analysis (EDA)

Checked data types, column names, and summary statistics
Identified null values and inconsistencies across columns

3. 🧹 Data Cleaning

Handled missing values — filled null Review Rating values with the category-level median using groupby().transform()
Standardized column names — converted to lowercase with underscores; renamed purchase_amount_(usd) → purchase_amount
Feature Engineering:

Created age_group column (Young Adult, Adult, Middle-aged, Senior) using pd.qcut()
Created purchase_frequency_days by mapping frequency labels (e.g., Weekly → 7, Monthly → 30) to numeric values


Removed redundant columns — dropped promo_code_used (found to be 100% identical to discount_applied)

4. 🗄️ SQL Queries (PostgreSQL)

Connected Python to a local PostgreSQL database (customer_behavior) using SQLAlchemy
Loaded the cleaned DataFrame into a customer table using df.to_sql()
Ran analytical SQL queries to extract business insights:

Total and average revenue by category
Top-spending age groups
Discount impact on purchase amounts
Purchase frequency distribution



5. 📊 Power BI Dashboard

Connected Power BI to the PostgreSQL database
Built interactive visuals including bar charts, pie charts, and slicers
Dashboard covers: revenue by category, age group analysis, discount trends, and geographic/seasonal breakdowns

6. 📄 Report & 📽️ Presentation

Created a structured analytics report using Gamma (AI report builder)
Designed a professional slide deck using Gamma to present findings to a non-technical audience


📊 Dashboard Preview
The Power BI dashboard includes the following pages:

Overview — KPIs: Total Revenue, Avg Purchase Amount, Avg Rating, Total Customers
Customer Demographics — Purchase behavior by age group and gender
Category Analysis — Revenue and frequency breakdown by product category
Discount & Promo Impact — How discounts influence purchase amounts and frequency
Purchase Patterns — Shipping preferences, payment methods, and purchase seasonality

To view the dashboard, open Customer_Shopping_Dashboard.pbix in Power BI Desktop.

📈 Key Results & Insights

Clothing was the top revenue-generating category across all demographics
Adult age group (mid-30s to mid-40s) drove the highest total purchase volume
Customers using discounts purchased more frequently but at lower average order values
Free Shipping was the most preferred shipping method, especially among high-frequency buyers
Credit Card and PayPal dominated as payment methods
promo_code_used was completely redundant with discount_applied — confirming data quality issues early in the pipeline


▶️ How to Run
Prerequisites:
Python 3.8+
PostgreSQL (with pgAdmin 4)
Power BI Desktop
Jupyter Notebook
Step 1 — Clone the Repository
bashgit clone https://github.com/your-username/customer-shopping-behavior-analysis.git
cd customer-shopping-behavior-analysis
Step 2 — Install Python Dependencies
bashpip install pandas sqlalchemy psycopg2-binary
Step 3 — Set Up the Database

Open pgAdmin 4
Create a new database named customer_behavior
Update credentials in the notebook:

pythonusername = "your_username"
password = "your_password"
port     = "5432"
Step 4 — Run the Notebook
bashjupyter notebook customer_shopping_behavior_analysis.ipynb
Step 5 — Open Power BI Dashboard

Open Customer_Shopping_Dashboard.pbix in Power BI Desktop
Update PostgreSQL credentials if prompted
Click Refresh

📁 Repository Structure
customer-shopping-behavior-analysis/
│
├── customer_shopping_behavior.csv
├── customer_shopping_behavior_analysis.ipynb
├── Customer_Shopping_Dashboard.pbix
├── report/
├── presentation/
└── README.md

👤 Author
[Rohith V]
Data Analyst | Python • SQL • Power BI
LinkedIn: https://www.linkedin.com/in/rohith-v-7065a6281/
GitHub: https://github.com/Rohithv0

This project was built as part of a personal data analytics portfolio to demonstrate end-to-end data skills across ingestion, cleaning, querying, visualization, and storytelling.

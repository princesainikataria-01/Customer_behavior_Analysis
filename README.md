Customer Behavior Analytics
1. Overview
Customer Behavior Analytics is an end-to-end data analytics project built around a customer shopping behavior dataset. The project uses Python for data inspection and cleaning, SQL Server for business-focused analysis, and Power BI for dashboarding.
The goal is to explore purchasing patterns, compare customer segments, and answer practical business questions about revenue, discounts, subscriptions, shipping, product ratings, and customer purchase history.
2. Dataset
- File: customer_shopping_behavior.csv
- Format: CSV
- Records: 3,900 rows
- Columns: 18 original columns
The dataset includes customer demographics and shopping details such as age, gender, item purchased, category, purchase amount, location, season, review rating, subscription status, shipping type, discounts, previous purchases, payment method, and purchase frequency.
Keep the dataset in the repository only if its source and license allow redistribution. Otherwise, add instructions for obtaining it and keep the data file out of GitHub.

3. Tools & Technologies
- Python: Data inspection, cleaning, feature creation, and preprocessing
- Pandas: Data manipulation and analysis
- Google Colab / Jupyter Notebook: Running the Python notebook
- Microsoft SQL Server: Querying and business analysis
- SQL Server Management Studio (SSMS): Executing SQL queries
- Power BI Desktop: Dashboard development
- GitHub: Project hosting and documentation
4. Project Workflow
Step 1: Load and inspect the data
The Python notebook reads the CSV into a Pandas DataFrame and inspects sample records, descriptive statistics, and missing values.
Step 2: Clean and prepare the data
The notebook includes these preparation steps:
- Fills missing Review Rating values using the median rating within each Category.
- Converts column names to lowercase and replaces spaces with underscores.
- Renames purchase_amount_(usd) to purchase_amount.
- Creates an age_group column using age quartiles, labelled Young Adult, Adult, Mid-Aged, and Senior.
- Maps purchase-frequency categories to approximate day intervals in a new purchase_frequency_days column.
- Checks whether discount_applied and promo_code_used match, then drops promo_code_used.
Step 3: Export the cleaned dataset
The notebook exports the prepared data as customer_behavior_cleaned.csv for use in later analysis.
Step 4: Analyze the data in SQL Server
The SQL script contains 10 business questions covering:
1. Revenue by gender.
2. Customers who used a discount but spent more than the average purchase amount.
3. Five products with the highest average review ratings.
4. Average purchase amount by Standard and Express shipping.
5. Average spend and total revenue for subscribers versus non-subscribers.
6. Products with the highest percentage of purchases using discounts.
7. Customer segmentation based on previous purchases.
8. Top three most-purchased products within each category.
9. Subscription status among repeat buyers with more than five previous purchases.
10. Revenue contribution by age group.
Step 5: Build the Power BI dashboard
The repository includes Customer Behavior Dashboard.pbix, the Power BI report file. Open it in Power BI Desktop and update its data-source settings if necessary.
The exact visuals and KPI values should be documented after confirming them in the dashboard.
Step 6: Report findings
Use the SQL results and Power BI visuals to summarize the most important patterns and business implications. Add verified numerical findings to this README once the analysis is finalized.
5. Dashboard
Power BI file: Customer Behavior Dashboard.pbix
To preview the dashboard on GitHub, export or capture a dashboard screenshot and save it as images/dashboard.png. Then add the following Markdown where the screenshot is stored:
![Customer Behavior Dashboard](images/dashboard.png)
6. Results & Insights
The SQL analysis is designed to investigate:
- Revenue differences across gender and age groups.
- Spending patterns among subscribers and non-subscribers.
- Discount usage and purchase amounts.
- Product ratings and popular products by category.
- Purchase behavior among new, returning, and loyal customer groups.
- Differences in average purchase amounts by shipping type.
Add your confirmed findings here, ideally with specific values from your SQL results or Power BI dashboard. No numerical business conclusions are included in this README because the query outputs and dashboard visuals have not been supplied for verification.
7. Repository Structure
customer-behavior-analytics/
├── customer_shopping_behavior.csv
├── DA_project.ipynb
├── Customer Behavior queries.sql
├── Customer Behavior Dashboard.pbix
├── images/
│   └── dashboard.png
└── README.md
The images/dashboard.png file is optional; add it after capturing a dashboard screenshot. If you choose to organize files into folders, update the paths in this structure accordingly.
8. How to Run the Project
Requirements
- Python 3.x
- Google Colab or Jupyter Notebook
- Pandas
- Microsoft SQL Server and SQL Server Management Studio (SSMS)
- Power BI Desktop
A. Run the Python notebook
1. Open DA_project.ipynb in Google Colab or Jupyter Notebook.
2. Upload customer_shopping_behavior.csv to the notebook environment, or update the CSV path to match your setup.
3. Run the cells in order.
4. Download the generated customer_behavior_cleaned.csv file.
Note: The notebook currently reads the input file from /content/customer_shopping_behavior.csv, which is a Google Colab path. Change this path when running locally.
B. Run the SQL queries
1. Open SQL Server Management Studio and connect to your SQL Server instance.
2. Import customer_behavior_cleaned.csv into a table named customer in your target database, or adjust the SQL script to match your chosen table and schema.
3. Confirm that the imported column names match those referenced by the queries, including purchase_amount, age_group, discount_applied, subscription_status, and previous_purchases.
4. Open Customer Behavior queries.sql and execute the queries individually or as a script.
5. Review the result sets and record the verified findings.
C. Open the Power BI dashboard
1. Open Customer Behavior Dashboard.pbix in Power BI Desktop.
2. If prompted, update the data source to your local cleaned dataset or SQL Server table.
3. Refresh the data.
4. Review the visuals and export a screenshot for the README if desired.
9. Skills Demonstrated
- Data loading, inspection, and cleaning with Python and Pandas
- Exploratory data analysis
- Feature engineering and data preprocessing
- SQL Server querying, aggregation, subqueries, CTEs, and window functions
- Customer segmentation and business-question analysis
- Power BI reporting and dashboard development
- Project documentation
10. Author
Prince Saini
- LinkedIn: https://www.linkedin.com/in/prince-saini-544577284/

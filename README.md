\# Dream Store Sales Dashboard



\## 📊 Project Overview

This project analyzes sales performance for \*\*Dream Store\*\* over a 4-year period (2022–2025).

The goal was to design a \*\*Power BI dashboard\*\* that provides executives and stakeholders with actionable insights into sales, returns, customer behavior, and operational efficiency.



The dashboard includes:

\- Key KPIs (Sales, Orders, Returns, Delivery Time, Return Rate)

\- Sales trends over time

\- Payment method distribution

\- Orders by day of the week

\- Top products by sales

\- Sales by promotion

\- Returns trend analysis



---



\## 🛠️ Data Preparation

The dataset was cleaned and transformed to ensure consistency across:

\- \*\*sales\_transactions\*\* (orders, amounts, dates, employees, products, payment methods)

\- \*\*returns\_log\*\* (returned orders and reasons)

\- \*\*shipping\_details\*\* (shipping and delivery dates)



Additional calculated columns were created to enrich the analysis.



---



\## 📐 DAX Measures



```DAX



\*\*-- Total Sales\*\*

Total Sales =

SUM ( sales\\\_transactions\\\[total\\\_amount] )



\*\*-- Total Orders\*\*

Total Orders =

DISTINCTCOUNT ( sales\\\_transactions\\\[transaction\\\_id] )



\*\*-- Average Order Value\*\*

Average Order Value =

DIVIDE ( \\\[Total Sales], \\\[Total Orders] )



\*\*-- Total Returns\*\*

Total Returns =

COUNTROWS ( returns\\\_log )



\*\*-- Return Rate\*\*

Return Rate =

DIVIDE ( \\\[Total Returns], \\\[Total Orders] )



\*\*-- Average Delivery Time (in days)\*\*

Average Delivery Time =

AVERAGEX (

\&nbsp;   shipping\\\_details,

\&nbsp;   DATEDIFF ( shipping\\\_details\\\[ship\\\_date], shipping\\\_details\\\[delivery\\\_date], DAY )

)



\*\*-- Return Rate (%)\*\*

Return Rate % =

DIVIDE ( \\\[Total Returns], \\\[Total Orders] )



\*\*🧩 Added Columns\*\*



\*\*-- Delivery Days (shipping\\\_details table)\*\*

Delivery Days = 

DATEDIFF ( shipping\\\_details\\\[ship\\\_date], shipping\\\_details\\\[delivery\\\_date], DAY )



\*\*-- Day of Week (sales\\\_transactions table)\*\*

Day of Week =

FORMAT ( sales\\\_transactions\\\[date], "dddd" )



\*\*-- Day of Week Number (sales\\\_transactions table)\*\*

Day of Week Number = 

SWITCH (

\&nbsp;   sales\\\_transactions\\\[Day of Week],

\&nbsp;   "Monday", 1,

\&nbsp;   "Tuesday", 2,

\&nbsp;   "Wednesday", 3,

\&nbsp;   "Thursday", 4,

\&nbsp;   "Friday", 5,

\&nbsp;   "Saturday", 6,

\&nbsp;   "Sunday", 7,

\&nbsp;   BLANK()

)



These columns were used to:



\* Calculate delivery performance
\* Visualize customer ordering patterns by weekday
\* Ensure correct sorting of weekdays in visuals



📊 Dashboard Features



\* KPI Cards: Total Sales, Total Orders, Avg. Order Value, Avg. Delivery Time, Total Returns, Return Rate
\* Sales Trends: Line chart by Year, Quarter, and Month
\* Payment Methods: Pie chart distribution
\* Orders by Day of Week: Bar chart (Monday–Sunday)
\* Top Products: Horizontal bar chart
\* Sales by Promotion: Treemap chart showing sales contribution by promotion campaigns
\* Returns Over Time: Line chart



📈 Key Insights (2022–2025)



\* \*\*Sales Growth:\*\* Sales peaked in 2023–2024 but showed signs of decline in 2025 (incomplete year).
\* \*\*Customer Behavior:\*\*

Orders are fairly balanced across the week, with Friday (1,476) and Monday (1,474) slightly stronger.

Midweek (Tue–Thu) shows a small dip, suggesting opportunities for targeted campaigns.

\* \*\*Payment Preferences:\*\* Credit cards and mobile payments dominate, while cash and bank transfers are less common.
\* \*\*Promotions:\*\* A small number of promotions (e.g., PROMO-00) drive the majority of sales, highlighting the importance of campaign strategy.
\* \*\*Returns:\*\* Return rate is ~5%, which is acceptable but worth monitoring.
\* \*\*Delivery:\*\* Average delivery time is 4 days, with most deliveries clustering around 3–5 days.
\* \*\*Top Products:\*\* A handful of products account for the majority of sales, showing strong concentration.



💡 \*\*Recommendations\*\*



\* \*\*Optimize Promotions:\*\* Since one promotion drives most sales, diversify campaigns to reduce dependency and test new strategies.
\* \*\*Boost Midweek Engagement:\*\* Launch flash sales or loyalty rewards Tue–Thu to balance order volume.
\* \*\*Weekend Optimization:\*\* Ensure mobile-first experiences and highlight leisure/impulse products for weekend shoppers.
\* \*\*Returns Analysis:\*\* Investigate top return reasons to reduce the 5% rate — especially product defects or incorrect shipments.
\* \*\*Delivery Improvements:\*\* Aim to reduce average delivery time below 4 days to improve customer satisfaction.
\* \*\*Product Diversification:\*\* Expand offerings beyond top sellers to reduce risk and capture new customer segments.



📂 Repository Structure



README.md → Project documentation (this file)

Assets/ → Logo

Data/ → raw files

PowerBI/ → PBIX file with dashboard + screenshots folder

Reports/ → Final report with the findings







🏆 Conclusion



This dashboard provides a comprehensive, executive-friendly view of Dream Store’s performance. It highlights sales trends, customer behavior, promotions, and operational efficiency, while surfacing areas for improvement. With ongoing monitoring and refinements, it can serve as a powerful decision-making tool for management.



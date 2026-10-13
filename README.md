# Skincare-Sales-Analysis
Skincare Store Sales & Profit Analysis
An Excel project analysing product revenue, gross profit, category performance and monthly sales trends for a fictional Singapore skincare store.

Project Overview
The goal was to turn a messy sales export into a clear business summary answering:
- Which products generate the highest revenue?
- Which skincare categories contribute the most revenue?
- How do revenue and gross profit change each month?
- What proportion of revenue remains as gross profit?
Tools: Microsoft Excel, Excel Tables, formulas, PivotTables and charts.
Data disclosure: This project uses synthetic practice data with simulated trends. The products, brands and sales do not represent a real business.
Dataset
Detail	Description
Period	January 2024–December 2025
Raw records	2,575 rows
Unique sales lines after deduplication	2,500
Products	20
Fictional brands	4
Categories	9
Channels	Physical store, website and marketplace
Currency	Singapore dollars (SGD)


The dataset includes product IDs, dates, quantities, selling prices, unit costs, discounts, returns, refunds and order statuses. Records marked Review were retained but excluded from reported results.
Data Cleaning
The original data was preserved on a separate worksheet. Cleaning and calculation steps were documented in the workbook.
Action	Purpose
Removed 75 duplicate line IDs	Prevent counting the same sales line twice
Cleaned order-status spaces and capitalisation	Make status labels consistent
Standardised category spelling	Combine labels such as “Sun Screen” and “Sunscreen”
Removed currency symbols and commas from prices, costs and refunds	Convert exported text into usable numbers
Standardised discounts	Store 15% as 15 for consistent calculations
Converted date text into Excel dates	Support monthly analysis
Flagged missing or non-positive quantities	Identify invalid sales records
Flagged missing, non-positive or above-S$100 unit prices	Identify questionable prices for review
Filled missing unit costs from the same product’s known costs	Support profit calculations under a fixed-unit-cost assumption
Matched product IDs to a standard name reference	Prevent spelling variations splitting product totals
Recalculated revenue, COGS and gross profit	Replace unreliable exported totals
Added an Include/Review status	Apply a consistent analysis filter


The S$100 price threshold is a screening rule for this dataset, whose normal unit prices range from S$4 to S$45. It is not a general rule for skincare retail.
Calculations
- Product revenue: Quantity × Unit price × (1 − Discount / 100) − Refund
- Cost of goods sold (COGS): Quantity × Final unit cost
- Gross profit: Product revenue − COGS
- Gross profit margin: Total gross profit / Total product revenue
Cancelled orders contribute zero revenue and zero COGS. Returned skincare is assumed unsellable, so its product cost remains in COGS.
Product revenue excludes shipping revenue. Gross profit excludes fulfilment costs, rent, salaries and other operating expenses; it is not net profit.
Analysis and Dashboard
The dashboard presents:
- Total product revenue, gross profit and gross profit margin.
- Top five products ranked by revenue.
- Revenue by skincare category.
- Monthly revenue and gross profit across 24 months.
Product and category summaries use PivotTables. The monthly summary uses SUMIFS with month-start date boundaries. Overall margin is calculated from totals rather than averaging transaction margins.
Key Findings
Total included revenue
The included sales generated S$98,753.65 in product revenue across the two-year period.
Top five products by revenue
Product	Revenue (SGD)	Gross profit (SGD)
Barrier Repair Cream	13,745.60	8,333.60
Daily SPF50 Sunscreen	10,754.90	6,497.90
Niacinamide Serum	10,535.70	6,355.70
Retinal Night Serum	8,435.25	4,274.25
Lightweight SPF50 Fluid	4,949.15	2,729.15


Barrier Repair Cream led product revenue. Among these five products, it also generated the highest gross profit.
Category performance
Category	Revenue (SGD)
Serum	32,086.65
Moisturiser	21,509.30
Sunscreen	15,704.05
Mask	9,544.70
Cleanser	8,876.65
Eye Care	4,787.20
Toner	3,091.00
Lip Care	1,864.10
Mist	1,290.00
Total	98,753.65


Serums accounted for approximately 32.5% of included revenue, followed by moisturisers and sunscreens.
Business Recommendations
- Review stock availability and replenishment needs for leading products, particularly Barrier Repair Cream.
- Compare product profitability within the serum category before expanding its assortment or purchasing volume.
- Use monthly revenue and profit together when reviewing promotions: higher revenue does not necessarily mean higher profitability.
- Improve source-data validation for prices, dates and quantities to reduce manual cleaning.
These are proposed actions based on a practice dataset, not proven outcomes or evidence that a promotion caused sales growth.
Validation
- Checked monthly revenue against the Dashboard total and category revenue total.
- Checked monthly gross profit against the Dashboard gross profit total.
- Used Sum, rather than Count, for monetary PivotTable fields.
- Filtered PivotTables to Include records.
- Kept top-product subtotals separate from all-product dashboard totals.
Limitations
- The data and trends are synthetic.
- Excluding unresolved records may affect totals and rankings.
- Missing costs were estimated using the same product’s recorded costs, assuming unit cost is constant in this dataset.
- The analysis does not measure inventory availability, marketing spend or causal promotion effects.
- Gross profit does not represent the store’s final earnings after operating expenses.

Skills Demonstrated
Data cleaning, Excel formulas, lookup tables, conditional aggregation, PivotTables, chart design, financial metric calculation, validation and business interpretation.
Author: Thiri Myat Thwe

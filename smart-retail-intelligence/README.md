# Smart Retail Intelligence 📊
### Retail Sales, Profitability & Inventory Analytics using Excel and Power BI

> **PGDM – Business Analytics Project**  
> **Tools:** Microsoft Excel · Microsoft Power BI · DAX  
> **Dataset:** Synthetic sample data created for academic demonstration

## Overview
Smart Retail Intelligence is a retail analytics project designed to help managers understand sales performance, product profitability, discount effectiveness, and inventory reorder risk. It demonstrates how business data can be transformed into clear, actionable recommendations.

**Important:** The included dataset and the results calculated from it are synthetic and illustrative. They do not represent a real company or actual retail performance.

## Business Problem
Retailers need to know:
- Which products and categories generate the most revenue and gross profit?
- How do sales and profit change over time?
- How do different discount levels relate to gross margin?
- Which products may need stock replenishment?
- How can managers use these insights to make better decisions?

## Project Objectives
1. Analyze revenue, gross profit, gross margin, units sold, and average order value.
2. Compare performance by month, store, category, and product.
3. Explore the relationship between discounts and profitability.
4. Apply a basic inventory reorder-point rule.
5. Design an interactive Power BI dashboard for business users.
6. Convert the analysis into practical recommendations.

## Repository Structure
```text
smart-retail-intelligence/
├── README.md
├── data/
│   └── Smart_Retail_Intelligence_Sample_Data.xlsx
├── report/
│   └── Smart_Retail_Intelligence_Project_Report.docx
├── dashboard/
│   └── README.md
└── docs/
    └── data_dictionary.md
```

## Dataset
The Excel workbook contains:
- `Sales_Data` — 1,000 synthetic transaction rows across 2025
- `Inventory_Data` — sample current-stock and reorder-point information
- `Product_Master` — product and category reference details
- `Read_Me` — definitions and dataset limitations

### Main fields
| Field | Description |
|---|---|
| `Order_ID` | Unique sample transaction identifier |
| `Order_Date` | Transaction date |
| `Store` | Fictional store name |
| `Product_ID` / `Product_Name` | Product identifier and name |
| `Category` | Product category |
| `Quantity` | Units sold |
| `Discount_Pct` | Discount as a decimal; `0.10` means 10% |
| `Revenue_INR` | Quantity multiplied by selling price |
| `Gross_Profit_INR` | Revenue minus total product cost |
| `Customer_ID` | Anonymous synthetic customer identifier |

## Methodology
1. **Data validation in Excel:** check duplicates, missing values, data types, and formula consistency.
2. **Data modelling in Power BI:** import the workbook and create suitable relationships between sales, product, and date tables.
3. **DAX measures:** calculate total revenue, gross profit, units sold, orders, gross margin, average order value, and average discount.
4. **Visualization:** create KPI cards, monthly trends, category/product comparisons, discount analysis, and inventory-risk visuals.
5. **Business interpretation:** turn the results into inventory, pricing, and product-performance recommendations.

## Key KPIs
Suggested dashboard KPIs:
- Total Revenue
- Total Gross Profit
- Gross Margin %
- Total Units Sold
- Total Orders
- Average Order Value
- Average Discount %

Example DAX measures (adjust table/column names if your Power BI model differs):

```DAX
Total Revenue = SUM(Sales_Data[Revenue_INR])

Total Gross Profit = SUM(Sales_Data[Gross_Profit_INR])

Total Units Sold = SUM(Sales_Data[Quantity])

Total Orders = DISTINCTCOUNT(Sales_Data[Order_ID])

Gross Margin % = DIVIDE([Total Gross Profit], [Total Revenue], 0)

Average Order Value = DIVIDE([Total Revenue], [Total Orders], 0)

Average Discount % = AVERAGE(Sales_Data[Discount_Pct])
```

## Inventory Reorder Logic
A simple reorder point is estimated as:

`Reorder Point = Average Daily Demand × Supplier Lead Time × Safety Factor`

A product is flagged for review when current stock is less than or equal to the reorder point. This is a basic planning rule, not an automatic purchase-order system. Real use should account for demand variability, open purchase orders, minimum order quantities, and supplier reliability.

## Dashboard Pages
Recommended Power BI report layout:
1. **Executive Overview:** revenue, gross profit, margin, units, and monthly trend
2. **Product & Category Analysis:** product rankings and category contribution
3. **Promotion Analysis:** discount levels compared with revenue and margin
4. **Inventory Risk:** current stock, reorder point, and items requiring review

Add screenshots of your completed dashboard to the `dashboard/` folder after you build it. Do not claim a dashboard is completed until you have actually created and validated it.

## Business Recommendations
- Review products at or below their reorder point before placing orders.
- Compare gross profit and margin as well as revenue when ranking products.
- Evaluate promotions using incremental profit, not sales volume alone.
- Use historical seasonality to support planning, then validate forecasts against unseen data.
- Reconcile Power BI totals with source records before using the dashboard for real decisions.

## Limitations
- The dataset is synthetic and for practice only.
- Discount comparisons do not prove that discounts caused a change in sales.
- The inventory table is a snapshot, not a complete stock-movement history.
- Forecasting should be validated using a suitable time-based test period before being used operationally.

## How to Use
1. Download or clone this repository.
2. Open the Excel workbook in `data/`.
3. Open Power BI Desktop and select **Home → Get Data → Excel workbook**.
4. Import the relevant sheets, check data types, create relationships, and add the DAX measures.
5. Build and validate the dashboard using the report layout above.
6. Save your `.pbix` file locally. Add screenshots to `dashboard/` if you want to showcase visuals publicly.

## Skills Demonstrated
- Data cleaning and validation
- Excel analysis and PivotTables
- KPI definition
- Power BI data modelling and dashboard design
- DAX measures
- Retail performance analysis
- Inventory planning logic
- Business insight communication

## Author
**Your Name**  
PGDM – Business Analytics  
*Replace this section with your name and relevant profile links before publishing.*

## License / Data Use
This is an academic demonstration project. The synthetic dataset is included for learning and portfolio demonstration. Do not upload confidential company or customer data.

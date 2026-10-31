# Data Dictionary

All records in the accompanying workbook are synthetic sample data created for educational use.

## Sales_Data
- `Order_ID`: unique sample transaction ID
- `Order_Date`: date of transaction
- `Store`: fictional store label
- `Product_ID`: product key
- `Product_Name`: product name
- `Category`: product category
- `Quantity`: units in transaction
- `List_Price_INR`: unit list price before discount
- `Discount_Pct`: discount rate as decimal (0.10 = 10%)
- `Selling_Price_INR`: unit price after discount
- `Revenue_INR`: quantity × selling price
- `Unit_Cost_INR`: unit product cost
- `Total_Cost_INR`: quantity × unit cost
- `Gross_Profit_INR`: revenue − total cost
- `Customer_ID`: anonymous synthetic customer key

## Inventory_Data
- `Current_Stock_Units`: illustrative stock snapshot
- `Avg_Daily_Demand_Units`: assumed average daily demand
- `Supplier_Lead_Time_Days`: assumed supplier lead time
- `Safety_Factor`: buffer multiplier
- `Reorder_Point_Units`: rounded-up average demand × lead time × safety factor
- `Stock_Status`: `Reorder` when current stock is at or below reorder point; otherwise `OK`

## Product_Master
Reference product, category, list price, unit cost, and sample reference stock fields.

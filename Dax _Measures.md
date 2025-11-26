# Task 1 - E-commerce DAX Measures

## Core Volume and Revenue Measures
Total Revenue = SUM('Orders'[Sales])
Total Orders = DISTINCTCOUNT('Orders'[OrderID])
Total Quantity = SUM('Orders'[OrderQuantity])

## Efficiency and Discount Measures
Total Discount Value = SUMX('Orders', 'Orders'[Discount] * 'Orders'[Sales])
Net Revenue (After Discount) = [Total Revenue] - [Total Discount Value]
Discount Rate % = DIVIDE([Total Discount Value], [Total Revenue], 0)
Avg Order Value (AOV) = DIVIDE([Total Revenue], [Total Orders])

## Profitability Measures (Based on Assumption)
Assumed Margin % = 0.30  // NOTE: Assumption due to missing COGS data
Assumed Gross Profit = [Total Revenue] * [Assumed Margin %]

## Target Tracking Measures (For Gauge Visual)
Net Revenue Target = 500000 
Net Revenue Max Gauge = [Net Revenue Target] * 1.2
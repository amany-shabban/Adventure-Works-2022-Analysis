# Adventure Works Sales Analysis - Power BI Project

## Project Overview

This Power BI project provides comprehensive sales analysis for Adventure Works Cycle, a multinational bicycle and cycling accessories manufacturer. The analysis covers sales transactions for bikes, components, clothing, and accessories across multiple territories and sales channels.

## Data Source

**Database**: AdventureWorks2022  
**Source**: Microsoft AdventureWorks sample database  
**Connection**: SQL Server (localhost)  
**Data Model**: Star Schema with custom SQL views

## Data Model

### Dimension Tables
- DimProducts
- DimSalesPersons
- DimTerritories
- DimShipMethods
- DimStatuses
- DimDate (Calculated Table)

### Fact Table
- FactOrderDetails


## DAX Measures

1. **No. Orders** - Distinct count of orders
2. **Total Quantity** - Sum of order quantities
3. **Subtotal** - Calculated as OrderQty × UnitPrice
4. **Total Tax** - Sum of tax amounts
5. **Total Freight** - Sum of freight charges
6. **Total Due** - Sum of total amounts due
7. **Sales Growth %** - Year-over-year sales growth percentage
8. **orderdate** - Orders count using OrderDate relationship
9. **ship date** - Orders count using ShipDate relationship
10. **due date** - Orders count using DueDate relationship

## Key Features

- Sales performance by product category and subcategory
- Territory and regional sales analysis
- Sales team performance tracking
- Order status monitoring
- Time-based analysis (order date, due date, ship date)
- Online vs offline channel comparison
- Year-over-year growth tracking

## Technical Implementation

**SQL Views Structure:**  
All dimension tables are sourced from custom SQL views (`vw_*`) created in the AdventureWorks2022 database.

**Date Dimension:**  
The DimDate table is dynamically generated using DAX CALENDAR function, covering the full date range from earliest OrderDate to latest DueDate.

**Measure Organization:**  
All measures are consolidated in the "All Measurs" table for centralized management.

## Usage Notes

1. The active relationship uses DueDateKey as default date context
2. Use orderdate/ship date measures for alternative time perspectives
3. Some orders have NULL SalesPersonID (online orders without assigned sales person)
4. Data grain is at order detail level (one row per product per order)

## Repository Structure

```
├── README.md
├── Insights_and_Recommendations.md
├── AdventureWorks.pbix
└── SQL/
    ├── vw_DimProducts.sql
    ├── vw_DimSalesPersons.sql
    ├── vw_DimTerritories.sql
    ├── vw_DimShipMethods.sql
    ├── vw_DimStatuses.sql
    └── vw_FactOrderDetails.sql
```

## Technical Requirements

- Power BI Desktop (latest version)
- SQL Server with AdventureWorks2022 database
- Network access to localhost SQL Server instance

## Author

Created as part of business intelligence analysis project using Microsoft Adventure Works sample database.

## License

This project uses the Adventure Works sample database, which is provided by Microsoft for educational and demonstration purposes.
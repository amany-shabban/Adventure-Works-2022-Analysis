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
The DimDate table is dynamically generated using DAX CALENDAR function, covering the full date range from earliest OrderDate to latest DueDate.

<table border="1">
    <tr>
        <td><img src="https://github.com/user-attachments/assets/abdac3ad-e877-4b31-b66f-72cfaff5eaf5" width="450"></td>
        <td><img src="https://github.com/user-attachments/assets/deeefa9b-d739-468c-95a9-4dc8ad75c1cd" width="450"></td>
    </tr>
    <tr>
        <td><img src="https://github.com/user-attachments/assets/ebce4a52-c8ed-4f77-8acc-ba5e7ecd933a" width="450"></td>
        <td><img src="https://github.com/user-attachments/assets/76775a7f-6267-4660-ac82-e4aaf5c1ad33" width="450"></td>
    </tr>
    <tr>
        <td><img src="https://github.com/user-attachments/assets/5ffc08c4-b63f-4bec-9fec-f4b99393bd17" width="450"></td>
        <td></td>
    </tr>
</table>


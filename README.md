# SQL Project - DWH_Customers Project
 
This project involves creating a new relational database named `DWH_Customers` based on the existing `Training` database. The project includes defining dimension and fact tables, creating stored procedures for data transfer and historical tracking, and setting up a time dimension table.

## Table of Contents

- Project Overview
- Database Structure
  - Dim_Customers Table
  - Fact_Sales Table
  - Dim_Date Table
- Stored Procedures
- Database Diagram
- Installation
- Usage
- Contributing
- License

## Project Overview

The `DWH_Customers` project aims to create a data warehouse for customer and sales data. This involves transferring data from the `Training` database, handling data modifications, and maintaining historical records.

## Database Structure

### Dim_Customers Table

A dimension table for customers.

- **Columns**:
  - `id`: Primary key
  - `custid`: Customer ID
  - `companyname`: Company Name
  - `country`: Country
  - `city`: City
  - `valid_from`: Valid From Date
  - `valid_to`: Valid To Date

### Fact_Sales Table

A snapshot fact table for sales.

- **Columns**:
  - `month_id` (yyyymm): Month ID
  - `id`: Customer ID (from `Dim_Customers`)
  - `Sales`: Sales Amount
  - `Discount_value`: Discount Value

### Dim_Date Table

A dimension table for time.

- **Columns**:
  - `iddate` (yyyymmdd): Date ID
  - `date` (yyyy-mm-dd): Date
  - `month_id` (yyyymm): Month ID
  - `year` (yyyy): Year

## Stored Procedures

### Transfer Customers Procedure

A stored procedure to transfer customers from the `Training` database to the `DWH_Customers` database, considering modifications and historical tracking.

### Load Fact_Sales Procedure

A stored procedure to load the `Fact_Sales` table using data from `Sales.Orders` and `Sales.OrderDetails` tables in the `Training` database for the years 2006 and 2007.

### Monthly Data Load Procedure

A stored procedure with a `reporting_date` parameter to load data for the previous month. This procedure should be run for the reporting dates of February, March, April, May, and June 2008.

## Database Diagram

A diagram of the new database structure will be defined and included here.

## Installation

Instructions for setting up the `DWH_Customers` database locally.

```bash
# Clone the repository
git clone https://github.com/MihaiMarianMacrea/SQL-Project
cd DWH_Customers

# Run the setup script
./setup.sh

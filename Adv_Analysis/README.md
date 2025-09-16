# Excel Employee Dashboard
## Overview
This project analyzes sales performance of a coffee chain using an Excel-based dashboard.
The dataset was retrieved on [Kaggle](https://www.kaggle.com/datasets/amruthayenikonda/coffee-chain-sales-dataset) with the goal to evaluate profitability, product performance, and market trends while comparing actual results to the business targets.

### Dashboard File
The final analysis dashboard: [Dashboard](Adv_Analysis.xlsx)

### The Dataset
- Area Code
- COGS (Cost of Goods Sold)
- Difference Between Actual and Target Profit
- Date
- Inventory Margin
- Margin (profit)
- Market Size
- Profit
- Sales

### Questions to Analyze
1. Which months and product/market combinations deviated most from the target profit?
2. Which states consistently exceed or miss targets by quarter?
3. Does decaf or regular have a better gross margin based on area?
4. Which products are the biggest profit drivers each quarter, and how does that change by state?

### Excel Skills Used
The following workbook uses the following skills:
- Pivot Tables
- Pivot Charts
- Slicers
- Power Query
- Power Pivot
- DAX (Data Analysis Expressions)

## Data Preparations
1. Extract
   - Using Power Query to extract the original data set ([Kaggle](https://www.kaggle.com/datasets/amruthayenikonda/coffee-chain-sales-dataset)) and create three queries
     1. First with all the coffe chain sales information
     2. Data query for sales transactions
     3. Geography query for the location of each coffe chain sales
    - **Disclamer:** The Data query and Geography query were created to practice my skills in using Power Pivot
2. Transform:
   - Transformed each query by changing the column types, remove unecessary columns, add an index column, separate the date column for different purposes, and reorder columns
3. Load:
   - Loaded all queries into the workbook
4. Power Pivot:
   - Data Model: Create relationships between the three tables using the index column and add create hierarchy for the date and geography table
   - Power Pivot Menu: Used to refine the data model and create measures
   
## Analysis
1. Which months and product/market combinations deviated most from the target profit?
   - **Purpose:**
   - **Pivot Table:**
   - **DAX:**
   - **Why it matters?**
2. Which states consistently exceed or miss targets by quarter?
   - **Purpose:**
   - **Pivot Table:**
   - **DAX:**
   - **Why it matters?**
3. Does decaf or regular have a better gross margin based on area?
   - **Purpose:**
   - **Pivot Table:**
   - **DAX:**
   - **Why it matters?**
4. Which products are the biggest profit drivers each quarter, and how does that change by state?
   - **Purpose:**
   - **Pivot Table:**
   - **DAX:**
   - **Why it matters?**
  

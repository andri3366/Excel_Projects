# Excel Employee Dashboard
## Overview
This employee analysis dashboard was created to help a company investigate various aspects of the variety of employees within the company. 
This data was acquired through [Kaggle](https://www.kaggle.com/datasets/tawfikelmetwally/employee-dataset), which provides an analysis of data using Excel functions and formulas. The data contains detailed information on education, city, joining year, etc. are presented here. 

### Dashboard File
The final dashboard: [Dashboard](Employees_Dashboard.xlsx)

## The Dataset
The dataset received from Kaggle is anonymized to protect the employees privacy, however after careful inspection it is determined the company is located in India. The dataset contains detailed information on:
- Education
- Joining Year
- City
- Payment Tier
- Age
- Gender
- Ever Benched (Employees who have been temporarily assigned without work)
- Experience in Current Domain
- Leaver or Not (binary:1 = Leave, 0 = Active)

### Excel Skills Used
The following Excel skills were utilized to complete the final analysis:
- Charts & Visulations
- Formulas & Functions
- Pivot table
- Data Validation

## The Dashboards
### Employees Currently Active Vs. on Leave 
- **Chart Type:** A vertical bar chart
- **Pivot Table:** An addictional Column called "Leave" was added, this column used an IF() function from the original "LeaveOrNot" column to assign "Leave" if the binary value equaled 1 and "Active" if the binary value contained 0.
  ```
  =IF([@LeaveOrNot]=1, "Leave", "Active")
  ```
- **Functions Used:**
  - COUNTIF() function was used to compare all employees in the "Gender" column to either "Female" or "Male"
  ```
  =COUNTIF(employee[Leave], B50)
  ```
  - UNIQUE() function to receive each of the different types of values.
  ```
  =UNIQUE(employee[Leave])
  ```
- **Insight Gained:** This enables quick insight of the total amount of employees active in comparison to those on leave. Approximately 34.4% of employees are on leave, a relativealy high value percentage that may sugest workforce issues.

### Employees Who Have Ever Been Benched 
- **Chart Type:** A vertical bar chart
- **Functions Used:** UNIQUE(), COUNTIF(), and IF()
- **Insight:** Indicates whether or not an employee has been temporarily assigned without work, approximately 11.4% of employees have been benched. This is not directly correlated with leave status.

### Employees Per City
- **Chart Type:** A vertical bar chart
- **Functions Used:** UNIQUE(), COUNTIF(), and IF()
  - I used two different IF() statement to determine if the selected value from the list matched another value from the UNIQUE() list. This allowed for the graph to display a different colour based on the selected value.
  ```
  =IF($B19<>cities,$C19,NA())
  =IF($B19=cities,$C19,NA())
  ```
- **Features:** Dropdown list for city selection
- **Insight** Shows employee distribution across Bangalore, Pune, and New Dehli

### Male Vs. Female Employees 
- **Chart Type:** A vertical bar chart
- **Functions Used:** UNIQUE(), COUNTIF(), and IF()
- **Features:** Dropdown list for gender selection
- **Insight** Visualizes gender representation within the company

### Degree Types per Joining Year Based on City and Gender 
- **Chart Type:** A vertical bar chart with grouped years
- **Functions Used:** 
  - TRANSPOSE(), SORT(), UNIQUE()
    ```
    =TRANSPOSE(SORT(UNIQUE(employee[JoiningYear]),1,1))
    ```
  - SUMPRODUCT()
    ```
    =SUMPRODUCT(
    (employee[[Education]:[Education]]=$O3)*
    (employee[[JoiningYear]:[JoiningYear]]=P$2)*
    (employee[[City]:[City]]=cities)* (employee[[Gender]:[Gender]]=sex)
    )
    ```
- **Insight** Tracks education distribution by joining year, filtered by gender and city

### Employees Who Have Been Benched While Being Active or on Leave Based on City and Gender
- **Chart Type:** A multi-dimensional bar chart
- **Functions Used:** 
  - TRANSPOSE(), SORT(), UNIQUE()
  - SUMPRODUCT()
    - For determining Active/Leave with Benched or Not Benched
    ```
    =SUMPRODUCT(
    (employee[[EverBenched]:[EverBenched]]=$R31) * (employee[[Leave]:[Leave]]=S$30) * (employee[[City]:[City]]=cities)* (employee[[Gender]:[Gender]]=sex)
    )
    ```
    - Sum of all Active/Leave or Benched/Not Benched based on city and gender
    ```
    =SUMPRODUCT(
    (employee[[City]:[City]]=cities)*(employee[[Gender]:[Gender]]=sex)*(employee[[Leave]:[Leave]]=S$30)
    )
    ```
- **Insight:** Shows interaction between benching status, activity, city, and gender

### Employee Look Up
- **Tools:** Employee ID Search
- **Features:** Displays employee's benching status and whether they are active or on leave

### Data Summary
Quick metrics using Excel formulas
- Total Employees ```COUNTA()```
- Average Age ```AVG()```
- Average Experience ```AVG()```
- Employees on Leave ```COUNTIF()```
- % of EMployees on Leave ```(COUNTIF() / COUNTA())```
- Total Benched Employees ```COUNTIF()```

## Data Validation 
- Used for dropdown filters (city and gender)
- Ensures consistent inputs
- Improves usability with sheet protection

## Future Improvements
- Build interactive visuals with Power BI
- Add trend analysis for payment tier, education, and experience level





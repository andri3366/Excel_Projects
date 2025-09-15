# Excel Employee Dashboard
## Overview
This employee analysis dashboard was created to help a company investigate various aspects of the variety of employees within the company. 
This data was acquired through Kaggle: https://www.kaggle.com/datasets/tawfikelmetwally/employee-dataset, which provides an analysis of data using Excel functions and formulas. The data contains detailed information on education, city, joining year, etc. are presented here. 

### Dashboard File
My final dashboard is located in...

### Excel Skills Used
The following Excel skills were utilized to complete the final analysis:
- Charts
- Formulas and Functions
- Data Validation

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
- Leaver or Not (Employees who are currently active or on leave)

## The Dashboards
### Employees Currently Active Vs. on Leave - Bar Chart
- A vertical bar chart was utilized for a better visual comparison of active Vs. leave.
- The graph remains stagnent as only there are 2 categorical entries ("Active", "Leave)
- Insight Gained: This enables quick insight of the total amount of employees active in comparison to those on leave. Based on the provided information it approximately 34.4% of employees are on leave, a relativealy high value, which indicate potential internal or external factors to have so many employees on leave.
- I used the UNIQUE() function to receive each of the different types of values.
- A COUNTIF() function was used to compare all employees in the "Gender" column to either "Female" or "Male"

### Employees Who Have Ever Been Benched - Bar Chart
- This caregory indicates whether or not an employee has been temporarily assigned without work, the datasets overview from Kaggle did not provide any insight on the duration for an employee to be considered benched. However, based on the provided information approximately 11.4% of employees have been benched. Therefore, it is important to note that an employee being benched is not directly correlated to currently being on leave.
- A bar chart was used to visualize the difference between the two categories.
- Within the pivot table I added an addictional Column called "Leave", this column used an IF() function from the original "LeaveOrNot" column to assign "Leave" if the binary value equaled 1 and "Active" if the binary value contained 0.
  - The dataset from Kaggle did not specify which of the binary values represented which, however using the bar chart distribution in the datasets preview to determine which of the binary values would represent "Leave" and "Active"
- A COUNTIF() function was used to compare all employees in the "Leave" column to either "Active" or "Leave"

### Employees Per City - Bar Chart
- Using the UNIQUE() function to determine the different cities the company is located ("Bangalore", "Pune", "New Dehli")
- A COUNTIF() function compares the "City" values to the unique values list
- Using Excel's data validation feature I create a drop-down list of each unique city value.
  -  Additionally, assigning the drop-down list cell a name for future analysis 
- Since user's can select different cities, I used two different IF() statement to determine if the selected value from the list matched another value from the UNIQUE() list. This allowed for the graph to display a different colour based on the selected value.

### Male Vs. Female Employees - Bar Chart
- Using similar approached to the bar charts above, for this graph I did use a data validation list as it was needed for another analysis.
  - By assigning the drop-down list cell a value and using IF() function to display different colours on the bar chart for better visualization.

### Degree Types per Joining Year Based on City and Gender - Bar Chart
- I used a UNIQUE() function to achieve the different city names acroos different rows
- Additionally using [code] to display the different joining years on one row spanning multiple columns.
- A SUMPRODUCT() function allowed for displayed results to vary based on the Education type, Joining Year, and selected city and gender from the drop down list.

### Employees Who Have Been Benched While Being Active or on Leave Based on City and Gender - Bar Chart
- UNQIUE() functions were used to create the data matrix
- Similarly to the graph above a SUMNPORUDCT() function provided the sum based on the required conditions
- Additionally SUM() functions are included to provide numerical representation between each graph.

### Employee Look Up
A simple dashboard was created to allow users to quickly search employees based on their number and display the results of if they have ever been benched or are currently on leave/active.

### Data
Another dashboard was added to display commonly required data based on the dataset. The dashboard displays the following data:
- Total Employees (COUNTA())
- Average Age (AVG())
- Average Experience (AVG())
- Employees on Leave (COUNTIF())
- % of EMployees on Leave (COUNTIF() / COUNTA())
- Total Benched Employees (COUNTIF())

## Data Validation 
Using the data validation feature in Excel allows user input to be predefined and prevent inconsistent entries.
By protecting each sheet overall usability is enhanced.

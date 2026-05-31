Data Leverage Project
Project Overview

This project demonstrates the use of Microsoft Power BI Power Query to perform data cleaning, transformation, integration, profiling, and automation tasks on multiple datasets. The project combines monthly sales data, employee information, and GDP data to create a structured and analysis-ready dataset.

Datasets Used
Sales Data Files
sales_jan.xlsx
sales_feb.xlsx
sales_march.xlsx
sales_apr.xlsx (used for refresh simulation)

Columns:

Order ID
Date
Sales Person
Product
Quantity
Unit Price
Total Amount
Employee Data File
employees_with_country.xlsx

Columns:

Employee ID
Employee Name
Department
Position
Joining Date
Salary
Reason
Country
GDP Dataset
Country GDP data sourced from IMF, World Bank, and United Nations statistics.
Power Query Transformations Performed
1. Basic Transformations
Removed blank rows and columns
Promoted first row as headers
Renamed columns with meaningful names
Changed data types appropriately
Removed duplicate records
Filtered null values
2. Numeric Transformations
Rounded Total Amount values to 2 decimal places
Created Cost column
Created Profit column using:

Profit = Total Amount − Cost

3. Date & Time Transformations
Extracted Day, Month, Year, and Quarter
Created Fiscal Month column
Calculated Years of Experience using Joining Date
4. Conditional Columns & Indexing

Created Sales Category:

High (≥ 10,000)
Medium (5,000–9,999)
Low (< 5,000)

Added:

Index_0 (0-based)
Index_1 (1-based)
5. Pivoting & Unpivoting
Pivoted monthly sales data into column format
Unpivoted columns back into normalized structure
6. Merging & Appending
Appended January–April sales files
Merged sales data with employee data using employee names
7. Grouping & Aggregation

Grouped data by Country and calculated:

Total Sales
Average Order Value
Transaction Count
8. Data Profiling & Quality

Used:

Column Quality
Column Distribution
Column Profile

To identify:

Missing values
Errors
Distinct values
Unique values
9. Parameters & Source Settings
Created dynamic FolderPath parameter
Configured Data Source Settings
Managed credentials and permissions
10. Refresh Simulation
Added sales_apr.xlsx
Refreshed Power BI model
Verified automatic data loading and transformation application
Challenges Faced
Employee Name Matching

Sales data and employee data contained different naming formats.

Solution:
Created helper columns and used Merge Queries with fuzzy matching.

Missing Country Information

Country column was unavailable after merge.

Solution:
Expanded the merged employee table and selected required columns.

Grouping Errors

Incorrect grouping configuration produced inaccurate results.

Solution:
Grouped data only by Country and applied proper aggregation functions.

Dynamic Data Refresh

Manual file loading was inefficient.

Solution:
Implemented parameterized folder paths and folder-based connections.

Tools Used
Microsoft Power BI Desktop
Power Query Editor
Microsoft Excel

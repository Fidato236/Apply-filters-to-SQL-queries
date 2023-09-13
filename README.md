# Apply-filters-to-SQL-queries
# Apply filters to SQL queries
Project description
This project involves a comprehensive examination of the organization's data, specifically focusing on the 'employees' and 'log_in_attempts' tables. The objective is to reinforce the organization's security framework by identifying and mitigating potential security threats. The core focus lies in the identification of anomalies within the login attempts data to ensure the safeguarding of critical data assets.
Retrieve after hours failed login attempts
Here's how this query works:

SELECT : This part of the query instructs the database to select all columns (represented by '') from the 'log_in_attempts' table. This means that all available information for each row that meets the specified conditions will be included in the query result.

FROM log_in_attempts: This specifies the source table for the query, which is the 'log_in_attempts' table.

WHERE login_time > "18:00" AND success = 0: This part of the query sets the conditions for filtering the data. It retrieves rows where two conditions are met:

login_time > "18:00": This condition checks the 'login_time' column and selects rows where the login time is later than 6:00 PM (18:00 in 24-hour format). This helps identify login attempts that occurred after normal working hours.
success = 0: This condition checks the 'success' column and selects rows where the login attempt was not successful (where 'success' equals 0). This focuses on failed login attempts.
By combining these conditions, the query retrieves records of failed login attempts that occurred after 6:00 PM, which can be valuable for identifying potential security issues or suspicious activities within the organization's systems.
 
Retrieve login attempts on specific dates
 
In the "Retrieve login attempts on specific dates" section of the SQL query template, the query is constructed to extract specific data from the 'log_in_attempts' table based on designated dates. Here's an overview of how this query functions:

SELECT: This component of the query instructs the database to retrieve all columns (represented by '*') from the 'log_in_attempts' table. Consequently, all available information for each row that fulfills the specified criteria will be included in the query result.

FROM log_in_attempts: This segment specifies the source table for the query, which, in this case, is the 'log_in_attempts' table.

WHERE login_date IN ('2022-05-09', '2022-05-08'): This portion of the query establishes the condition for data filtration based on specific dates. It retrieves rows where the 'login_date' column matches either of the two specified dates: May 9, 2022, or May 8, 2022.

The outcome of this query will encompass all login attempts that transpired on the provided dates. This information can be instrumental for scrutinizing user login patterns, detecting any unusual login activities on these particular dates, or monitoring login events for auditing and security purposes.Retrieve login attempts outside of Mexico
 
Retrieve login attempts outside of Mexico" section of the SQL query template, the query is designed to retrieve specific information from the 'log_in_attempts' table for login attempts that originate from locations outside of Mexico. 
Here's how this query works:

SELECT : This part of the query instructs the database to select all columns (represented by '') from the 'log_in_attempts' table. This means that all available information for each row meeting the specified conditions will be included in the query result.

FROM log_in_attempts: This specifies the source table for the query, which is the 'log_in_attempts' table.
WHERE NOT country LIKE "MEX%": This part of the query specifies the condition. It filters the data to include only rows where the 'country' column does not match any value that starts with "MEX". The % symbol is a wildcard character in SQL, representing any number of characters. So, "MEX%" matches any country code that begins with "MEX," and NOT negates this condition to include countries that do not match.
Both your original condition and this one achieve the same result of retrieving login attempts from locations outside of Mexico. The choice between them depends on your preference and the specific requirements of your analysis.
Retrieve employees in Marketing
To create a SQL query that identifies all employees in the Marketing department for all offices in the East building, you can use the following query:
 
Here's a description of how this query works:

SELECT *: This part of the query selects all columns from the "employees" table for the matching rows.

FROM employees: Specifies that you're querying the "employees" table.

WHERE department = 'Marketing': This condition filters rows where the "department" column is equal to 'Marketing', selecting only employees in the Marketing department.

AND office LIKE 'East%': This condition filters rows where the "office" column starts with 'East', using the % wildcard to match any characters that follow. This ensures that you select employees in offices located in the East building.

This query will retrieve all employees who work in the Marketing department and have offices in the East building.
Retrieve employees in Finance or Sales
 
Here's how this query works:

SELECT *: This part of the query selects all columns from the "employees" table for the matching rows.

FROM employees: Specifies that you're querying the "employees" table.

WHERE department IN ('Finance', 'Sales'): This condition filters rows where the "department" column matches either 'Finance' or 'Sales'. The IN clause allows you to specify multiple values to match against.

This query will retrieve all employees who work in either the Finance or Sales department, providing you with a list of employees from these two departments.
Retrieve all employees not in IT
 
Here's how this query works:

SELECT *: This part of the query selects all columns from the "employees" table for the matching rows.

FROM employees: Specifies that you're querying the "employees" table.
WHERE NOT clause is used to negate the condition, so it selects all rows where the "department" column is not equal to 'Information Technology.'
Summary
This project involves an in-depth analysis of the organization's data, specifically targeting the 'employees' and 'log_in_attempts' tables, with a primary objective of strengthening the organization's security framework by identifying and mitigating potential security threats. The project encompasses several SQL query sections, each tailored to address distinct data retrieval scenarios.

Retrieve After Hours Failed Login Attempts:

This query is designed to identify failed login attempts that occurred after business hours. It selects records from the 'log_in_attempts' table where login attempts took place after 6:00 PM and were unsuccessful. This data is valuable for spotting potential security issues or suspicious activities outside of regular working hours.
Retrieve login attempts on specific dates:
The query in this section focuses on retrieving login attempts on the specified dates, which have been updated to '2022-05-09' or '2022-05-08'. It selects data from the 'log_in_attempts' table where the 'login_date' matches either of these two dates. This query aids in analyzing login patterns, tracking events for auditing purposes, and identifying any unusual activity on the new dates.
Retrieve Login Attempts Outside of Mexico:

This query aims to extract information from the 'log_in_attempts' table related to login attempts originating from locations outside of Mexico. It selects records where the 'country' column does not start with "MEX." This can help identify login activity from international sources, potentially indicating unauthorized access.
Retrieve Employees in Marketing:

In this section, the query identifies all employees working in the Marketing department across offices located in the East building. It selects data from the 'employees' table, filtering for employees in the Marketing department ('department = 'Marketing'') and those working in East building offices ('office LIKE 'East%'').
Retrieve Employees in Finance or Sales:

This query retrieves a list of employees working in either the Finance or Sales departments. It selects data from the 'employees' table where the 'department' matches either 'Finance' or 'Sales.' This provides a consolidated list of employees from these two departments.
Retrieve All Employees Not in IT:

The final query extracts data from the 'employees' table, selecting all employees except those in the Information Technology department ('WHERE NOT department = 'Information Technology''). This query generates a comprehensive list of employees from various departments excluding IT.
These SQL queries serve as powerful tools for accessing and managing data, enabling organizations to perform targeted analyses, enhance security measures, and make informed decisions based on specific data retrieval needs.

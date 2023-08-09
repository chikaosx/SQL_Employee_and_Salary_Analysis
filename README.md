# SQL_Employee_and_Salary_Analysis

**SQL Queries Report: Employee and Salary Analysis**


**Introduction:**

This report provides an overview of SQL queries performed on an employee and salary database. The database contains employee information such as names, cities, dates of birth, and email addresses, as well as salary details. The queries focus on filtering and analyzing this data to extract valuable insights.

**Query 1: Filtering by City**

The first query aimed to retrieve employee data from the database based on their city of residence. The SQL query used the `IN` operator to filter for employees located in Mumbai and Delhi. This query allows for identifying employees in these specific cities, potentially for regional analysis or targeted communication.
```
SELECT * FROM employee WHERE city IN ('Mumbai', 'Delhi');
```
![](city.png)

**Query 2: Name Pattern Matching**

The second query focused on extracting employees whose first names contained both 'a' and 'e'. By utilizing the `LIKE` operator with wildcards, the database was queried for names meeting this specific pattern. This type of analysis could be used for identifying names that share certain characteristics, which might be of interest for various purposes, such as naming trends.
```
SELECT * FROM employee WHERE fname LIKE '%a%' AND fname LIKE '%e%';
```
![](name.png)

**Query 3: Date of Birth Analysis**

The third query involved selecting employees based on their date of birth. The query filtered out employees born after the year 1990, using the `YEAR` function to extract the birth year from the date of birth. This analysis could be useful for demographic studies or for identifying younger employees in the organization.
```
SELECT * FROM employee WHERE YEAR(date_of_birth) > 1990;
```
![](dob.png)

**Query 4: Salary Insights**

The fourth query was focused on the salary table. It aimed to extract salary data below 1 million and sort it in ascending order. This query allows for examining salary distribution, identifying potential outliers, or understanding the range of compensation within the organization.
```
SELECT * FROM salary WHERE Base < 1000000 ORDER BY Base ASC;
```
![](salary.png)

**Query 5: Email Manipulation**

The final query was an update statement that modified the email addresses of employees. It removed the domain '@gmail.com' from the email addresses. This action could be performed for various reasons, such as standardizing email addresses or preparing data for integration with other systems.
```
UPDATE employee
SET email = SUBSTRING(email, 1, LEN(email) - 10)
WHERE email LIKE '%@gmail.com';
```
![](email.png)

**Conclusion:**

The SQL queries performed on the employee and salary database provided valuable insights and allowed for data extraction and manipulation. These queries demonstrated how SQL can be used to filter and analyze data based on specific criteria, revealing patterns, trends, and anomalies within the dataset. The results of these queries can be leveraged for strategic decision-making, data cleaning, and further analysis in a business context.

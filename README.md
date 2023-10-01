<!-----

Yay, no errors, warnings, or alerts!

Conversion time: 0.93 seconds.


Using this Markdown file:

1. Paste this output into your source file.
2. See the notes and action items below regarding this conversion run.
3. Check the rendered output (headings, lists, code blocks, tables) for proper
   formatting and use a linkchecker before you publish this page.

Conversion notes:

* Docs to Markdown version 1.0β34
* Sun Oct 01 2023 12:15:46 GMT-0700 (PDT)
* Source doc: Apply filters to SQL queries
----->



# Apply filters to SQL queries


## Project description

Part of my job at the organization I work for is to investigate security issues to help keep the system secure. Recently I’ve discovered some potential security issues that involve login attempts and employee machines. The following steps show how I used SQL with filters to examine the organization’s data and investigate the potential security issues.  


## Retrieve after hours failed login attempts

A potential security threat occurred after business hours (18:00) regarding failed login attempts. The following code demonstrates how I created a SQL query to filter for failed login attempts that occurred after business hours:  

![image2](https://github.com/markach151/FilterSQLQueries/assets/84886088/cb229339-b5dd-4f41-802d-b60311589cfa)

The first block of code in the screenshot is my query, and the second part is a portion of the output. To investigate the security threat I needed to query the `log_in_attempts` table and review all failed login attempts that occurred after 18:00. I accomplished this by using a `WHERE` clause with an `AND` operator to filter the results that I needed. The first condition is `login_time > '18:00'`, which filters for login attempts that occurred after 18:00. The second condition is `success = 0`, which filters for failed login attempts. ` `    


## Retrieve login attempts on specific dates

A suspicious event occurred on 2022-05-09. All login attempts which occurred on this day and the day before need to be reviewed. The following code demonstrates how I used filters in SQL to create a query that identifies all login attempts occurring on 2022-05-09 or 2022-05-08:

![image4](https://github.com/markach151/FilterSQLQueries/assets/84886088/0bc2eb63-1ee7-4882-bb3b-7924485ef712)

The first part of the screenshot is my query, and the second part is a portion of the output. This query returns all login attempts that occurred on 2022-05-09 or 2022-05-08. First, I selected all data from the `log_in_attempts` table. I used a `WHERE` clause with an `OR` operator to filter my results including login attempts only on 2022-05-09 or 2022-05-08. The first condition is `login_date = '2022-05-08'` and the second condition is `login_date = '2022-05-09'`. These conditions filter for logins on the two specific dates. 


## Retrieve login attempts outside of Mexico

There’s been suspicious activity with login attempts, but this activity didn’t originate from Mexico. I need to investigate login attempts that occurred outside of Mexico. The following code demonstrates how I used filters in SQL to create a query that identified all login attempts occurring outside of Mexico:

![image6](https://github.com/markach151/FilterSQLQueries/assets/84886088/c9e54be1-a410-4336-a796-1b4cf920baaa)

The first part of the screenshot is my query, and the second part is a portion of the output. This query returns all login attempts that occurred in countries besides Mexico. First, I started by selecting all data from the  `log_in_attempts` table. I used a `WHERE `clause with `NOT` to filter for countries other than Mexico. I used `LIKE` with `MEX%` as the pattern to match because the dataset represents Mexico as `MEX` and `MEXICO`. The percentage sign (`%`) substitutes for any number of characters when used with `LIKE`.


## Retrieve employees in Marketing

My team wants to perform security updates on specific employee machines in the Marketing department. I am responsible for getting information on these employee machines. The following code demonstrates how I used filters in SQL to create a query that identified all employees in the Marketing department in the East building: 

![image3](https://github.com/markach151/FilterSQLQueries/assets/84886088/3470e620-7876-46e2-8c97-c59c83852714)

The first part of the screenshot is my query, and the second part is a portion of the output. This query returns all employees in the marketing department in the East building.  First, I started by selecting all data from the `employees` table. I used a `WHERE` clause with the `AND` operator to filter for employees who work in the Marketing department and in the East building. The first condition is `department = 'Marketing'`, which filters for employees in the Marketing department. The second condition is the `office LIKE 'East%'` section, which filters for employees in the East building. The `LIKE` keyword with `%` filter was needed because the East building has specific office numbers. 


## Retrieve employees in Finance or Sales

My team needs to perform a different security update on machines for employees in the Sales and Finance departments. The following code demonstrates how I used filters in SQL to create a query that identified all employees in the Sales or Finance department:  

![image5](https://github.com/markach151/FilterSQLQueries/assets/84886088/1710a926-bd38-4a5d-931e-a47e287f89a4)

The first part of the screenshot is my query, and the second part is a portion of the output. This query returns all employees in the Finance and Sales departments. First, I started by selecting all data from the `employees` table. I used a `WHERE` clause with `OR` to filter for employees who are in the Finance and Sales departments. The first condition is `department = 'Finance'`, which filters for employees from the Finance department. The second condition is `department = 'Sales'`, which filters for employees from the Sales department. The `OR` operator was used because I wanted employees from both departments.


## Retrieve all employees not in IT

MY team needs to make one more update to employee machines. The employees who are in the Information Technology department already had this update, but employees in all other departments need it. The following code demonstrates how I used filters in SQL to create a query which identified all employees not in the IT department:

![image1](https://github.com/markach151/FilterSQLQueries/assets/84886088/d3016d44-3c63-4392-9ff7-2849efdf47b9)

The first part of the screenshot is my query, and the second part is a portion of the output. The query returns all employees not in the Information Technology department. First, I started by selecting all data from the `employees` table. Then, I used a `WHERE` clause with `NOT` to filter for employees not in this department.


## Summary

In these tasks I examined the organization’s data in their `employees` and `log_in_attempts` tables. I used SQL filters to retrieve records from different datasets and investigated the potential security threats. 

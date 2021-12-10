# Pewlett-Hackard-Analysis
## Overview
We are creating queries in a SQL database to identify the employees at Pewlett Hackard that are about to retire. We will also run a separate query to identify the employees that are eligible for the Mentorship Program.

## Results
### Number of Retiring Employees by Title
After running the queries for employees eligible for retirement by having birth dates between January 1, 1952 and December 31, 1955, we observe the following results:
- At Pewlett-Hackard, There are 90,398 total employees eligible for retirement
- The titles of those employees are, in descending order:
    - Senior Engineer - 29,414
    - Senior Staff - 28,254
    - Engineer - 14,222
    - Staff - 12,243
    - Technique Leader - 4,502
    - Assistant Engineer - 1,761
    - Manager - 2

### List of Employees Eligible for the Mentorship Program
- There are 1,549 employees eligible to participate in the Mentorship Program. They are defined as employees born between January 1, 1965 and December 31, 1965.
- The query used to create the mentorship_eligibility table returns the full list of names of the mentors and specifies only the title they currently occupy with the company.

## Summary
Pewlett-Hackard will have 90,398 employees retiring soon. We would like to know what portion of the employee population may be retiring.
Using the below query, we see that Pewlett-Hackard currently has 300,024 total employees, which means they should anticipate almost a third of their workforce needing to be transitioned in the near future.

SELECT COUNT (emp_no) as "Number of Total Employees"
FROM employees;

We can also run a query to group the mentorship-eligible employees by department:

SELECT COUNT(emp_no) as "Number of Mentors",
    title
FROM mentorship_eligibility
GROUP BY title
ORDER BY "Number of Mentors" DESC;

From the result we can see there is nobody of the Manager position eligible to become a mentor, while there are two Managers eligible to retire. Pewlett-Hackard will need to come up with an arrangement to transition new employees to fill the Manager role if no mentors are available.
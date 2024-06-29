# 020 - Employee Salaries
## Problem

Write a query that prints a list of employee names (i.e.: the name attribute) for employees in **Employee** having a salary greater than
**$2000**per month who have been employees for less than **10** months. Sort your result by ascending employee_id.

## INPUT FORMAT

The **EMPLOYEE** table containing employee data for a company is described as follows:
| Column	    | Type   |
|-------------|--------|
| employee_id	| Integer|
| name	      | String |
| months	    | Integer|
| salary	    | Integer|

where employee_id is an employee's ID number, name is their name, months is the total number of months they've been working for 
the company, and salary is their monthly salary.

## SAMPLE INPUT 

| employee_id | name    | months | salary |
|-------------|---------|--------|--------|
|    12228    | Rose    | 15     | 1968   |
|    33645  	| Angela  | 1      | 3443   |
|    45692	  | Frank   | 17     | 1608   |
|    56118    | Patrick | 7      | 1345   |

The Name column only contains uppercase (A-Z) and lowercase (a-z) letters.

## SAMPLE OUTPUT 
```
Angela
Michael
Todd
Joe
```
##EXPLANATION
Angela has been an employee for 1 month and earns $3443 per month.
Michael has been an employee for 6 months and earns $2017 per month.
Todd has been an employee for 5 months and earns $3396 per month.
Joe has been an employee for 9 months and earns $3573 per month.
We order our output by ascending employee_id.

## Solution
```sql
SELECT NAME
FROM EMPLOYEE
WHERE SALARY > 2000 AND MONTHS < 10
ORDER BY EMPLOYEE_ID;
```

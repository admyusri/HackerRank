# 019 - Employee Names
## Problem

Write a query that prints a list of employee names (i.e.: the name attribute) from the **Employee** table in alphabetical order.

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
|-------------|---------|--------|
|    12228    | Rose    | 15     | 1968   |
|    33645  	| Angela  | 1      | 3443   |
|    45692	  | Frank   | 17     | 1608   |
|    56118    | Patrick | 7      | 1345   |
The Name column only contains uppercase (A-Z) and lowercase (a-z) letters.

## SAMPLE OUTPUT 
```
Angela
Bonnie
Frank
```

## Solution
```sql
SELECT NAME
FROM EMPLOYEE
ORDER BY NAME;
```

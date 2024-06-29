# 029 - Top Earners
## Problem

We define an employee's total earnings to be their **monthly salary X months** worked, and the maximum total earnings to be the maximum 
total earnings for any employee in the **Employee** table. Write a query to find the maximum total earnings for all employees as well as
the total number of employees who have maximum total earnings. Then print these values as 2 space-separated integers.

## INPUT FORMAT

The **EMPLOYEES** table containing employee data for a company is described as follows:
| Column	 | Type          |
|--------|---------------|
| employee_id	   | Integer        |
| name	 | String |
| months	 | Integer  |
| salary	 | Integer  |

where employee_id is an employee's ID number, name is their name, months is the total number of months they've been working for 
the company, and salary is the their monthly salary.

##Sample Input
| employee_id | name     | months | salary |
|----|----------|------| 
| 12228	 | Kristeen | 1420 |
| 2 | Ashley   | 2006 |
| 3	 | julia    | 2210 |
| 4	 | Maria    | 3000 |

##Sample Output
``2061``

##Explanation
The table below shows the salaries without zeros as they were entered by Samantha:
| ID | Name     | Salary |
|----|----------|------| 
| 1	 | Kristeen | 142 |
| 2	 | Ashley   | 26 |
| 3	 | julia    | 221 |
| 4	 | Maria    | 3 |

Samantha computes an average salary of **98.00**. The actual average salary is **2159.00**.

The resulting error between the two calculations is **2159.00 - 98.00 = 2061.00**. Since it is equal to the integer **2061**,
it does not get rounded up.

## Solution
```sql
select ceil(avg(salary) - avg(replace(salary, '0', '' ) ))
from employees;
```

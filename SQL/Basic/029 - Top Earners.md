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
| employee_id | name    | months | salary |
|-------------|---------|--------|--------|
|    12228    | Rose    | 15     | 1968   |
|    33645  	| Angela  | 1      | 3443   |
|    45692	  | Frank   | 17     | 1608   |
|    56118    | Patrick | 7      | 1345   |

##Sample Output
``69952 1``

##Explanation
The table and earnings data is depicted in the following diagram:
| employee_id | name    | months | salary | earnings |
|-------------|---------|--------|--------| 29520 |
|    12228    | Rose    | 15     | 1968   | 3443 |
|    33645  	| Angela  | 1      | 3443   | 27336 |
|    45692	  | Frank   | 17     | 1608   | 9415 |
|    56118    | Patrick | 7      | 1345   | 25630 |

The maximum earnings value is ** 69952**. The only employee with earnings= **69952**  is Kimberly, so we print the maximum earnings value (**69952**) and a count of the number of employees who have earned **$69952** (which is **1**) as two space-separated values.

## Solution
```sql
SELECT salary * months AS earnings, COUNT(*)
FROM Employee
GROUP BY earnings
ORDER BY earnings DESC
LIMIT 1;
```

# 011 - Placements
## Problem

You are given three tables: Students, Friends and Packages. Students contains two columns: ID and Name. Friends contains two columns: ID and Friend_ID (ID of the ONLY best friend). 
Packages contains two columns: ID and Salary (offered salary in $ thousands per month).

**Students**
| Column | Type    |
|--------|---------|
| ID | integer |
| Name	| String |

**Friends**
| Column | Type    |
|--------|---------|
| ID | integer |
| Friend_ID	| integer |

**Packages**
| Column | Type    |
|--------|---------|
| ID | integer |
| Salary	| Float |

Write a query to output the names of those students whose best friends got offered a higher salary than them. Names must be ordered by the salary amount offered to the best friends. 
It is guaranteed that no two students got same salary offer.

## Sample Input 

Students Table:
|ID| Name |
|--------|--------|
|1|Ashley|
|2|Samantha|
|3|Julia|
|4|Scarlet|

Friends Table:
|ID| Friend_ID |
|--------|--------|
|1|2|
|2|3|
|3|4|
|4|1|

Packages Table:
|ID| Salary |
|--------|--------|
|1|15.20|
|2|10.06|
|3|11.55|
|4|12.12|

## Sample Output 

```
Samantha
Julia
Scarlet
```

## Explanation

See the following table:
|ID| Name | Salary | Friend ID| Friend Salary|
|--------|--------|--------|--------|--------|
|1|Ashley|15.20|2|10.06|
|2|Samantha|10.06|3|11.55|
|3|Julia|11.55|4|12.12|
|4|Scarlet|12.12|1|15.20|

Now,
- Samantha's best friend got offered a higher salary than her at 11.55
- Julia's best friend got offered a higher salary than her at 12.12
- Scarlet's best friend got offered a higher salary than her at 15.2
- Ashley's best friend did NOT get offered a higher salary than her

The name output, when ordered by the salary offered to their friends, will be:
- Samantha
- Julia
- Scarlet

## Solution
```sql

```

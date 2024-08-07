# 012 - Symmetric Pairs
## Problem

You are given a table, Functions, containing two columns: X and Y.

| Column | Type    |
|--------|---------|
| X | integer |
| Y	| integer |

Two pairs (X1, Y1) and (X2, Y2) are said to be symmetric pairs if X1 = Y2 and X2 = Y1.

Write a query to output all such symmetric pairs in ascending order by the value of X. List the rows such that X1 ≤ Y1.

## Sample Input 

Students Table:
|X|Y|
|--------|--------|
|20|20|
|20|20|
|20|21|
|23|22|
|22|23|
|21|20|

## Sample Output 

```
20 20
20 21
22 23
```

## Solution
```sql
SELECT f1.X, f1.Y FROM Functions AS f1 
WHERE f1.X = f1.Y AND
(SELECT COUNT(*) FROM Functions WHERE X = f1.X AND Y = f1.Y) > 1
UNION
SELECT f1.X, f1.Y from Functions AS f1
WHERE EXISTS(SELECT X, Y FROM Functions WHERE f1.X = Y AND f1.Y = X AND f1.X < X)
ORDER BY X;
```

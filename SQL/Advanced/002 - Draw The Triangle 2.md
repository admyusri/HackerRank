# 002 - Draw The Triangle 2
## Problem

P(R) represents a pattern drawn by Julia in R rows. The following pattern represents P(5):

## Sample Output 

```
* 
* * 
* * * 
* * * * 
* * * * *
```

Write a query to print the pattern P(20).

## Solution
```sql
set @number = 0;
select repeat('* ', @number := @number + 1) from information_schema.tables limit 20;
```

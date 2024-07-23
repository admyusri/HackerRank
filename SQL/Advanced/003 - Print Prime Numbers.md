# 003 - Print Prime Numbers
## Problem

Write a query to print all prime numbers less than or equal to *1000*. Print your result on a single line, and use the ampersand (*&*) character as your separator (instead of a space).

For example, the output for all prime numbers <10 would be:
## Sample Output 

```
2&3&5&7
```

## Solution (Oracle)
```sql
select listagg(Prime_Number,'&') within group(order by Prime_Number)
from (select L Prime_Number from
     (select Level L 
     from Dual
     connect by Level <= 1000),
     (select Level M
     from Dual
     connect by Level <= 1000)
     where M <= L
     group by L
     having count(case when L/M = trunc(L/M) then 'Y' end) = 2
     order by L);
```

# 012 - Weather Observation Station 7
## Problem

Query the list of CITY names ending with vowels (i.e., a, e, i, o, or u) from **STATION**. Your result cannot contain duplicates.

## INPUT FORMAT

The **STATION** table is described as follows:
| Field	 | Type          |
|--------|---------------|
| ID	   | NUMBER        |
| CITY	 | VARCHAR2 (21) |
| STATE	 | VARCHAR2 (2)  |
| LAT_N	 | NUMBER        |
| LONG_W | NUMBER        |

where **LAT_N** is the northern latitude and **LONG_W** is the western longitude.

## Solution
```sql
SELECT DISTINCT CITY 
FROM STATION 
WHERE CITY LIKE '%a' OR CITY LIKE '%e'  OR CITY LIKE '%i'  OR CITY LIKE '%o'  OR CITY LIKE '%u';
```

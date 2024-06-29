# 016 - Weather Observation Station 11
## Problem

Query the list of CITY names from **STATION** that either do not start with vowels or do not end with vowels. Your result cannot contain duplicates.


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
WHERE (CITY NOT LIKE 'A%' AND CITY NOT LIKE 'E%'  AND CITY NOT LIKE 'I%'  AND CITY NOT LIKE 'O%'  AND CITY NOT LIKE 'U%') OR
(CITY NOT LIKE '%a' AND CITY NOT LIKE '%e'  AND CITY NOT LIKE '%i'  AND CITY NOT LIKE '%o'  AND CITY NOT LIKE '%u') ;
```

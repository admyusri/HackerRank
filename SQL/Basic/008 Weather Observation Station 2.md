# 008 - Weather Observation Station 2
## Problem

Query the following two values from the __STATION__ table:
1. The sum of all values in LAT_N rounded to a scale of **2** decimal places.
2. The sum of all values in LONG_W rounded to a scale of **2** decimal places.

## Input Format

The **STATION** table is described as follows:
| Field	 | Type          |
|--------|---------------|
| ID	   | NUMBER        |
| CITY	 | VARCHAR2 (21) |
| STATE	 | VARCHAR2 (2)  |
| LAT_N	 | NUMBER        |
| LONG_W | NUMBER        |

where LAT_N is the northern latitude and LONG_W is the western longitude.

## Output Format
Your results must be in the form:
```sql
lat lon
```
where ***lat*** is the sum of all values in LAT_N and ***lon*** is the sum of all values in LONG_W. Both results must be rounded to a scale of **2**  decimal places.

## Solution
```sql
SELECT CAST(ROUND(SUM(LAT_N),2) AS NUMERIC(7,2)),
       CAST(ROUND(SUM(LONG_W),2) AS NUMERIC(7,2))
FROM STATION;
```

# 008 - Weather Observation Station 2
## Problem

Query the following two values from the STATION table:
1. The sum of all values in LAT_N rounded to a scale of  decimal places.
2. The sum of all values in LONG_W rounded to a scale of  decimal places.

## Input Format

The STATION table is described as follows:
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
## Solution
```sql
lat lon
```
where  is the sum of all values in LAT_N and  is the sum of all values in LONG_W. Both results must be rounded to a scale of  decimal places.

## Solution
```sql
SELECT CITY, STATE FROM STATION;
```

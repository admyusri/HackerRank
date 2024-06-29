# 025 - Average Population
## Problem

Query the average population for all cities in **CITY**, rounded down to the nearest integer.

## INPUT FORMAT

The **CITY** table is described as follows:
| Field	 | Type          |
|--------|---------------|
| ID	   | NUMBER        |
| NAME	 | VARCHAR2 (17) |
| COUNTRYCODE	 | VARCHAR2 (3)  |
| DISTRICT	 | VARCHAR2 (20)         |
| POPULATION | NUMBER        |

## Solution
```sql
select floor(avg(population))
from city;
```

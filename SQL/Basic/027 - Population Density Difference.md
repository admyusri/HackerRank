# 027 - Population Density Difference
## Problem

Query the difference between the maximum and minimum populations in **CITY**.

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
select (max(population) - min(population))
from city;
```

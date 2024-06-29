# 023 - Revising Aggregations - The Sum Function
## Problem

Query the total population of all cities in **CITY** where District is **California**.

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
select sum(population)
from city
where district='California';
```

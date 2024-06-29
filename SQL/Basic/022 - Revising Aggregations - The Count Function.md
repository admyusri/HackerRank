# 022 - Revising Aggregations - The Count Function
## Problem

Query a count of the number of cities in **CITY** having a Population larger than **100,000**.

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
select count(name)
from city
where population > 100000;
```

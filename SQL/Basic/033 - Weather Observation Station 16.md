# 033 - Weather Observation Station 16
## Problem

Query the smallest Northern Latitude (LAT_N) from **STATION** that is greater than **137.2345**. Round your answer to **4** decimal places.

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
select round (min(lat_n), 4)
from station
where lat_n > 38.7780;
```

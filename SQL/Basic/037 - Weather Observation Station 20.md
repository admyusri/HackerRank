# 037 - Weather Observation Station 20
## Problem

A *median* is defined as a number separating the higher half of a data set from the lower half. Query the median of the Northern Latitudes (LAT_N) from **STATION** and round your answer to **4** decimal places.

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
SET @rowIndex := -1;
SELECT ROUND(AVG(t.LAT_N),4) FROM
(SELECT @rowIndex:= @rowIndex+1 AS rowIndex, s.LAT_N from STATION AS s ORDER BY s.LAT_N) AS t
where t.rowIndex in (floor(@rowIndex/2), ceil(@rowIndex/2));
```

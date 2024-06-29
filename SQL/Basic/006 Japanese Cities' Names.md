# 006 - Japanese Cities' Names
## Problem

Query the names of all the Japanese cities in the **CITY** table. The **COUNTRYCODE** for Japan is *JPN*.

The **CITY** table is described as follows:
| Field	 | Type          |
|--------|---------------|
| ID	   | NUMBER        |
| CITY	 | VARCHAR2 (17) |
| COUNTRYCODE	 | VARCHAR2 (3)  |
| DISTRICT	 | VARCHAR2 (20)         |
| POPULATION | NUMBER        |

## Solution
```sql
SELECT NAME FROM CITY WHERE COUNTRYCODE = 'JPN';
```

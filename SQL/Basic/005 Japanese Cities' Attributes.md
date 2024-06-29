# 005 - Japanese Cities' Attributes
## Problem

Query all attributes of every Japanese city in the **CITY** table. The **COUNTRYCODE** for Japan is *JPN*.

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
SELECT * FROM CITY WHERE COUNTRYCODE='JPN';
```

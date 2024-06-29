# 022 - Revising Aggregations - The Count Function
## Problem

Query a count of the number of cities in **CITY** having a Population larger than **100,000**.

## INPUT FORMAT

The **CITY** table is described as follows:
| Field	   | Type   |
|------------|--------|
| ID	     | String |
| NAME | String |

Occupation will only contain one of the following values: **Doctor, Professor, Singer** or **Actor**.

## SAMPLE INPUT 

An **OCCUPATIONS** table that contains the following records:
| Name    | Occupation|
|---------|---------|
| Samantha| Doctor|
| Julia  	| Actor | 
| Maria	  | Actor | 
| Meera   | Singer| 

## SAMPLE OUTPUT 
```
Ashely (P)
Christeen (P)
Jane (A)
Julia (A)
Ketty(P)
Maria(A)
Meera(S)
Priya(S)
Samantha(D)
There are a total of 2 doctors.
There are a total of 2 singers.
There are a total of 3 actors.
There are a total of 3 professors.
```
##EXPLANATION
The results of the first query are formatted to the problem description's specifications.
The results of the second query are ascendingly ordered first by number of names corresponding to each profession 
**(2 < 2 < 3 < 3)**, and then alphabetically by profession **(doctor < singer, and actor < professor)**.

## Solution
```sql
SELECT CONCAT (NAME, '(', (LEFT(OCCUPATION,1)), ')' )
FROM OCCUPATIONS
ORDER BY NAME;
```

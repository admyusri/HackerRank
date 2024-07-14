# 021 - The PADS
## Problem

Generate the following two result sets:
1. Query an alphabetically ordered list of all names in **OCCUPATIONS**, immediately followed by the first letter of each profession
   as a parenthetical (i.e.: enclosed in parentheses). For example: AnActorName(A), ADoctorName(D), AProfessorName(P), and ASingerName(S).
3. Query the number of ocurrences of each occupation in **OCCUPATIONS**. Sort the occurrences in ascending order, and output them in
   the following format:
`There are a total of [occupation_count] [occupation]s.`

where [occupation_count] is the number of occurrences of an occupation in **OCCUPATIONS** and [occupation] is the lowercase occupation name.
If more than one Occupation has the same [occupation_count], they should be ordered alphabetically.

**Note:** There will be at least two entries in the table for each type of occupation.
## INPUT FORMAT

The **OCCUPATIONS** table is described as follows:
| Column	   | Type   |
|------------|--------|
| Name	     | String |
| Occupation | String |

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
## EXPLANATION
The results of the first query are formatted to the problem description's specifications.
The results of the second query are ascendingly ordered first by number of names corresponding to each profession 
**(2 < 2 < 3 < 3)**, and then alphabetically by profession **(doctor < singer, and actor < professor)**.

## Solution
```sql
select concat(name, '(', substring(occupation, 1, 1), ')') as name
from occupations
order by name;

select concat('There are a total of', ' ', count(occupation), ' ', 
lower(occupation), 's.') as profession
from occupations
group by occupation
order by profession;
```

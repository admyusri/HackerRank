# 006 - Top Competitors
## Problem

Julia just finished conducting a coding contest, and she needs your help assembling the leaderboard! Write a query to print the respective hacker_id and name of hackers who achieved 
full scores for more than one challenge. Order your output in descending order by the total number of challenges in which the hacker earned a full score. If more than one hacker received full scores 
in same number of challenges, then sort them by ascending hacker_id.

## Input Format
The following tables contain contest data:
- Hackers: The hacker_id is the id of the hacker, and name is the name of the hacker.

| Column | Type    |
|--------|---------|
| hacker_id | integer |
| Name	| string |

- Difficulty: The difficult_level is the level of difficulty of the challenge, and score is the score of the challenge for the difficulty level.

| Column | Type    |
|--------|---------|
| difficulty_level | integer |
| score	| integer |

- Challenges: The challenge_id is the id of the challenge, the hacker_id is the id of the hacker who created the challenge, and difficulty_level is the level of difficulty of the challenge.

| Column | Type    |
|--------|---------|
| challenge_id | integer |
| hacker_id | integer |
| difficulty_level	| integer |

-Submissions: The submission_id is the id of the submission, hacker_id is the id of the hacker who made the submission, challenge_id is the id of the challenge that the submission belongs to,
and score is the score of the submission.

| Column | Type    |
|--------|---------|
| submission_id | integer |
| hacker_id | integer |
| challenge_id | integer |
| score	| integer |

## Sample Input

Hackers Table:
|hacker_id| Name |
|--------|--------|
|5580|Rose |
|8439|Angela |
|27205|Frank |
|52243|Patrick |
|52348|Lisa |
|57645|Kimberly |
|77726|Bonnie |
|83082|Michael |
|86870|Todd |
|90411|Joe |

Difficulty Table:
|difficulty_level| score |
|--------|--------|
|1|20 |
|2|30 |
|3|40 |
|4|60 |
|5|80 |
|6|100 |
|7|120 |

Challenges Table:
|challenge_id| hacker_id | difficulty_level|
|--------|--------|--------|
|4810|77726 | 4 |
|21089|27205 | 1 |
|36566|5580 | 7 |
|66730|52243 | 6 |
|71055|52243 | 2 |

Submissions Table:
| submission_id|challenge_id| hacker_id | score|
|--------|--------|--------|--------|
|68628|77726|36566 | 30 |
|65300|77726|21089 | 10 |
|40326|52243|36566 | 77 |
|8941|27205|4810 | 4 |
|83554|77726|66730 | 30 |

## Sample Output

```
90411 Joe
```
## Explanation

Hacker 86870 got a score of 30 for challenge 71055 with a difficulty level of 2, so 86870 earned a full score for this challenge.

Hacker 90411 got a score of 30 for challenge 71055 with a difficulty level of 2, so 90411 earned a full score for this challenge.

Hacker 90411 got a score of 100 for challenge 66730 with a difficulty level of 6, so 90411 earned a full score for this challenge.

Only hacker 90411 managed to earn a full score for more than one challenge, so we print the their hacker_id and name as **2** space-separated values.

## Solution
```sql
select h.hacker_id, h.name
from submissions s
join hackers h
on h.hacker_id = s.hacker_id
join challenges c 
on c.challenge_id = s.challenge_id
join difficulty d
on d.difficulty_level = c.difficulty_level 
where d.score = s.score
group by h.hacker_id, h.name
having count(*) > 1
order by count(*) desc, h.hacker_id;
```

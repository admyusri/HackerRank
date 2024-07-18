# 009 - Contest Leaderboard
## Problem

You did such a great job helping Julia with her last coding contest challenge that she wants you to work on this one, too!

The total score of a hacker is the sum of their maximum scores for all of the challenges. Write a query to print the hacker_id, name, and total score of the hackers ordered by the descending score. 
If more than one hacker achieved the same total score, then sort the result by ascending hacker_id. Exclude all hackers with a total score of 0 from your result.

## Input Format
The following tables contain contest data:
- Hackers: The hacker_id is the id of the hacker, and name is the name of the hacker.

| Column | Type    |
|--------|---------|
| hacker_id | integer |
| name	| string |

- Submissions: The submission_id is the id of the submission, hacker_id is the id of the hacker who made the submission, challenge_id is the id of the challenge for
  which the submission belongs to, and score is the score of the submission.

| Column | Type    |
|--------|---------|
| submission_id	| integer |
| hacker_id | integer |
| challenge_id | integer |
| score| integer |

## Sample Input 

Hackers Table:
|hacker_id| name |
|--------|--------|
|4071|Rose|
|4806|Angela |
|26071|Frank |
|49438|Patrick |
|74842|Lisa|
|80305|Kimberly|
|84072|Bonnie |
|87868|Michael |
|92118|Todd |
|95895|Joe|

Submissions Table:
|submission_id| hacker_id |challenge_id|score|
|--------|--------|--------|--------|
|67194|74842|63132|76|
|64479|74842 |19797|98|
|40742|26071 |49593|20|
|17513|4806 |49593|32|
|69846|80305|19797|19|

## Sample Output 

```
4071 Rose 191
74842 Lisa 174
84072 Bonnie 100
4806 Angela 89
26071 Frank 85
80305 Kimberly 67
49438 Patrick 43
```

## Explanation

Hacker 4071 submitted solutions for challenges 19797 and 49593, so the total score = 95 + max(43,96) = 191.

Hacker 74842 submitted solutions for challenges 19797 and 63132, so the total score = max(98,5) + 76 = 174 

Hacker 84072 submitted solutions for challenges 49593 and 63132, so the total score = 100 + 0 = 100.

The total scores for hackers 4806, 26071, 80305, and 49438 can be similarly calculated.

## Solution
```sql
select m.hacker_id, h.name, sum(score) as total_score from
(select hacker_id, challenge_id, max(score) as score
from Submissions group by hacker_id, challenge_id) as m
join Hackers as h
on m.hacker_id = h.hacker_id
group by m.hacker_id, h.name
having total_score > 0
order by total_score desc, m.hacker_id;
```

# 002 - Python If-Else
## Task

Given an integer, `n`, perform the following conditional actions:

- If `n` is odd, print `Weird`
- If `n` is even and in the inclusive range of 2 to 5, print `Not Weird`
- If `n` is even and in the inclusive range of 6 to 20, print `Weird`
- If `n` is even and greater than 20, print `Not Weird`

#### Input Format
A single line containing a positive integer, `n`.

#### Constraints
1 <= n <= 100

#### Output Format
Print `Weird` if the number is weird; otherwise, print `Not Weird`.

#### Sample Input 0
```
3
```

#### Sample Output 0
```
Weird
```
#### Explanation 0
*n=3*
*n* is odd and odd numbers are weird, so print Weird.

#### Sample Input 1
```
24
```
#### Sample Output 1
```
Not Weird
```
#### Explanation 1
*n=24*
*n* > 20 and *n* is even, so it is not weird.

#### Given Code

```python
import math
import os
import random
import re
import sys

if __name__ == '__main__':
    n = int(input().strip())
```

## Solution 1

```python
def weirdo (num):
    if num % 2 != 0:
        return "Weird"
    else: 
        if 2 <= num <= 5:
            return "Not Weird"
        elif 6 <= num <= 20:
            return "Weird"
        else:
            return "Not Weird"
        
N = int(input().strip())       
print(weirdo(N))        
```



## Solution 2

```python
def odd(num):
    if num % 2 != 0:
        return "Weird"
    else:
        return even(num)

def even(num):
    if 2 <= num <= 5:
        return "Not Weird"
    elif 6 <= num <= 20:
        return "Weird"
    elif num > 20:
        return "Not Weird"

N = int(input().strip()) 
print(odd(N))
```

# 005 - Loops
## Task
The provided code stub reads and integer `n` from STDIN. For all non-negative integers `i < N`, print **i<sup>2</sup>**. 

### Example
*n=3*
The list of non-negative integers that are less than *n=3* is *(0,1,2)*. Print the square of each number on a separate line.
```
0
1
4
```

#### Input Format
The first and only line contains the integer, `n`.


#### Constraints
1 <= N <= 20

#### Output Format

Print `n` lines, one corresponding to each `i`.

```
Sample Input 0
5
```

```
Sample Output 0
0
1
4
9
16
```

#### Given Code

```python
if __name__ == '__main__':
    n = int(input())
```


## Solution 1

```python
if __name__ == '__main__':
    n = int(input())

    for i in range(n):
        print(i**2)
```


## Solution 2

```python
if __name__ == '__main__':
    n = int(input())
    i = 0
    while i < n:
        r = i * i
        i = i + 1
        print(r)
```

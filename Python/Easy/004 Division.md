# 004 - Division
## Task
The provided code stub reads two integers, `a` and `b`, from STDIN.
Add logic to print two lines. The first line should contain the result of integer division,  `a` // `b` . The second line should contain the result of float division, `a`/`b` .

No rounding or formatting is necessary.

#### Example
*a=3*
*b=5*
- The result of the integer division *3 // 5 = 0*.
- The result of the float division is *3 // 5 = 0.6*.

Print
```
0
0.6
```

#### Input Format

- The first line contains the first integer, `a`.
- The second line contains the second integer, `b`.

#### Output Format

Print the two lines as described above.

```
Sample Input 0
4
3
```

```
Sample Output 0
1
1.33333333333
```

#### Given Code

```python
if __name__ == '__main__':
    a = int(input())
    b = int(input())
```

## Solution 1

```python
if __name__ == '__main__':
    a = int(input())
    b = int(input())

    print(int(a / b))
    print(float(a / b))
```

## Solution 2

```python
if __name__ == '__main__':
    a = int(input())
    b = int(input())

    def division_int(x,y):
        return x // y

    def division_flt(x,y):
        return x / y

    print(division_int(a,b))
    print(division_flt(a,b))
```

## Prime
``` Python
def isPrime(n):
    if n == 1:
        return False
    for x in range(2, n):
        if n % x == 0:
            return False
    else:
        return True

```

```python
def PrimeList(n):
    prime = []
    for i in range(2, n+1):
        for j in range(2, i):
            if i % j == 0:
                break
        else:
            prime.append(i)
    return prime
```
---
## Factorial
``` Python
def factorial(n):
    if n == 0:
        return 1
    else:
        return n * factorial(n - 1)
```

``` Python
def factorial(n):
    fact = 1
    for i in range(1, n+1):
        fact = fact * i
    return fact
```

---
## Palindrome
```python
def palindrome(str):
    if str == str[::-1]:
        return True
    else:
        return False
```

```python
def palindrome(num : int):
    if num < 0:
        return False
    elif num == 0:
        return True
    else:
        return palindrome(num // 10) and (num % 10 == num // 10 % 10)
```

---
## Armstrong

```python
def isArmstrong(n):
    sum = 0
    for i in str(n):
        sum += int(i)**len(str(n))
    if sum == n:
        return True
    else:
        return False
```



> Human beings face ever more complex and urgent problems, and their effectiveness in dealing with these problems is a matter that is critical to the stability and continued progress of society.

\- Doug Engelbart, 1961


---

- Number Theory
- Dynamic Programming
- Combination
- Backtracking 
- subsequences problem
- Graph
- bit manipulation
- Greedy
- Arrays
- [[#Factorial|Factorial]]
- [[#Drawing an English Ruler|Drawing an English Ruler]]
- [[#Binary Search|Binary Search]]
- [[#Fibonacci|Fibonacci]]
- [[#Types Of Recursion|Types Of Recursion]]
	- [[#Types Of Recursion#Linear Recursion|Linear Recursion]]
	- [[#Types Of Recursion#Binary Recursion|Binary Recursion]]
- [[#Designing Recursive Algorithms|Designing Recursive Algorithms]]

Recursion is a technique by which a function makes one or more calls to itself during execution, or by which a data structure relies upon smaller instances of the very same type of structure in its representation.

- The *factorial function* (commonly denoted as n!) is a classic mathematical function that has a natural recursive definition. 
- An *English ruler* has a recursive pattern that is a simple example of a fractal structure. 
- *Binary search* is among the most important computer algorithms. It allows us to efficiently locate a desired value in a data set with upwards of billions of entries. 
- The *file system* for a computer has a recursive structure in which directories can be nested arbitrarily deeply within other directories. Recursive algorithms are widely used to explore and manage these file systems.


## Factorial

$$
n! =
\begin{cases}
1, &\text{if $n$ = 0 } \\
n.(n-1)! , &\text{if $n$ >0}\\
\end{cases}
$$
```python
def factorial(n):
    if n == 0:
        return 1
    else:
        return n*factorial(n-1)
```
![[Pasted image 20230118143624.png]]
Each time a function (recursive or otherwise) is called, a structure known as an activation record or frame is created to store information about the progress of that invocation of the function. This activation record includes a namespace for storing the function call’s parameters and local variables and information about which command in the body of the function is currently executing. When the execution of a function leads to a nested function call, the execution of the former call is suspended and its activation record stores the place in the source code at which the flow of control should continue upon return of the nested call. This process is used both in the standard case of one function calling a different function, or in the recursive case in which a function invokes itself. The key point is that there is a different activation record for each active call

## Drawing an English Ruler

In general, an interval with a central tick length L ≥ 1 is composed of: 
-  An interval with a central tick length L−1 
- A single tick of length L 
- An interval with a central tick length L−1

```python
def draw_line(tick_length, tick_label= ''):
    """Draw one line with given tick length (followed by optional label)."""
    line = '-'*tick_length
    if tick_label:
        line += ' '+tick_label
    print(line)

def draw_interval(center_length):
    #Draw tick interval based upon a central tick length
    if center_length>0: # stop when length drops to 0
        draw_interval(center_length-1)  # recursively draw top ticks
        draw_line(center_length) # draw center tick
        draw_interval(center_length - 1) # recursively draw bottom ticks

def draw_ruler(num_inches, major_length):
    #Draw English ruler with given number of inches, major tick length
    draw_line(major_length, '0' ) # draw inch 0 line
    for j in range(1, 1 + num_inches):
        draw_interval(major_length - 1) # draw interior ticks for inch
        draw_line(major_length, str(j)) # draw inch j line and

draw_ruler(3,3)
```

```bash
--- 0
-
--
-
--- 1
-
--
-
--- 2
-
--
-
--- 3
```

![[Pasted image 20230118152711.png]]

## Binary Search

![[Pasted image 20230118162925.png]]

We consider three cases: 
- If the target equals data[mid], then we have found the item we are looking for, and the search terminates successfully. 
- If target < data[mid], then we recur on the first half of the sequence, that is, on the interval of indices from low to mid−1. 
- If target > data[mid], then we recur on the second half of the sequence, that is, on the interval of indices from mid+1 to high.

## Fibonacci

$$
\begin{cases}
F0 = 0 \\
F1 = 1 \\
Fn = Fn−2 +Fn−1 ,& \text{ for n > 1}.
\end{cases}
$$
```python
def bad_fibonacci(n):
    if n <= 1:
        return n
    else :
        return bad_fibonacci(n-1)+bad_fibonacci(n-2)
```

Unfortunately, such a direct implementation of the Fibonacci formula results in a terribly inefficient function. Computing the nth Fibonacci number in this way requires an exponential number of calls to the function.


```python
def good_fibonacci(n):
    """”Return pair of Fibonacci numbers, F(n) and F(n-1)"""
    if n <=1:
        return (n,0)
    else:
        (a,b) = good_fibonacci(n-1)
        print(a,b)
        return (a+b,a)

```

In terms of efficiency, the difference between the bad recursion and the good recursion for this problem is like night and day. The bad fibonacci function uses exponential time. We claim that the execution of function good fibonacci(n) takes O(n) time.

## Types Of Recursion

- If a recursive call starts at most one other, we call this a linear recursion. 
- If a recursive call may start two others, we call this a binary recursion. 
- If a recursive call may start three or more others, this is multiple recursion.

### Linear Recursion

If a recursive function is designed so that each invocation of the body makes at most one new recursive call, this is know as **linear recursion.**

- **Summing the Elements of a Sequence Recursively**
```python
def linear_sum(S, n):
    """Return the sum of the first n numbers of sequence S."""
    if n==0:
        return 0
    else:
        return linear_sum(S, n-1) + S[n-1]
```
![[Pasted image 20230119122604.png]]

- **Reversing a Sequence with Recursion**

```python
def reverse(S,start,stop):
    if start < stop-1:
        S[start], S[stop-1] = S[stop-1], S[start]
        reverse(S,start+1,stop-1)
    return S

```

- **Recursive Algorithms for Computing Powers**

```python
def power(x,n):
    if n==0:
        return 1
    else:
        return x*power(x,n-1)

```


```python
def power(x,n):
    if n==0:
        return 1
    else:
        partial = power(x,n//2)
        res = partial*partial
        if n%2 == 1:
            res *= x
    return res
```

![[Pasted image 20230119153549.png]]

### Binary Recursion

When a function makes two recursive calls, we say that it uses *binary recursion.*

```python
def binary_sum(S,start,stop):
    if start >= stop:
        return 0
    elif start == stop-1:
        return S[start]
    else:
        mid =  (start+stop)//2
        return binary_sum(S,start,mid) + binary_sum(S,mid,stop)
```

![[Pasted image 20230119164626.png]]

## Designing Recursive Algorithms

In general, an algorithm that uses recursion typically has the following form: 
- Test for base cases. We begin by testing for a set of base cases (there should be at least one). These base cases should be defined so that every possible chain of recursive calls will eventually reach a base case, and the handling of each base case should not use recursion. 

- Recur. If not a base case, we perform one or more recursive calls. This recursive step may involve a test that decides which of several possible recursive calls to make. We should define each possible recursive call so that it makes progress towards a base case

A successful recursive design sometimes requires that we redefine the original problem to facilitate similar-looking subproblems. Often, this involved reparameterizing the signature of the function. For example, when performing a binary search in a sequence, a natural function signature for a caller would appear as binary search(data, target). we defined our function with calling signature binary search(data, target, low, high), using the additional parameters to demarcate sublists as the recursion proceeds. This change in parameterization is critical for binary search. If we had insisted on the cleaner signature, binary search(data, target), the only way to invoke a search on half the list would have been to make a new list instance with only those elements to send as the first parameter. However, making a copy of half the list would already take O(n) time, negating the whole benefit of the binary search algorithm.



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

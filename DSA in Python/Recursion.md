
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

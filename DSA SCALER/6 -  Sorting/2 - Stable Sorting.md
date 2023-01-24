## Bubble Sort

Bubble sort is one of the simplest and most straightforward sorting algorithms that work by comparing elements in a list, which are adjacent (next to each other) and then swapping them, until the largest(or smallest) of them reaches its correct order.

**Working :**
1.  Begin with the first element.
2.  Compare the current element with the next element.
3.  If the current element is greater than the next element, then swap both the elements. If not, move to the next element.
4.  Repeat steps 1 – 3 until we get the sorted list.

![[Pasted image 20230124121633.png]]

- In bubble sort, to sort a list of length n, we need to perform n – 1 iterations.
- After each iteration, the largest among the unsorted elements was placed at its position.

### Algorithm

We just saw that to sort a list of n elements using bubble sort, we need to perform n – 1 iteration. And for each iteration, we need to :

-   Run a loop over the entire list or array.
-   Compare the element at the index i with the element at (i+1).
-   If the element at i is greater than the element at (i+1), swap both the elements
-   Else, move to the next element.

**Time Complexity :** O(n^2)
**Space Complexity :** 
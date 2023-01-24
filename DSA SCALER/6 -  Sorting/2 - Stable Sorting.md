## Bubble Sort

Bubble sort algorithm repeatedly compares the adjacent elements and swaps them if not in order.

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

1.  Run a loop over the entire list or array.
2.  Compare the element at the index i with the element at i + 1.
3.  If the element at i is greater than the element at i + 1, swap both the elements
4.  Else, move to the next element.

**Time Complexity :** O(n^2)
**Space Complexity :** O(1)

```python
# Bubble sort in Python
 
def bubbleSort(arr):
    
  # loop over array elements
  for i in range(len(arr)):
 
    # loop to compare array elements
    for j in range(0, len(arr) - i - 1):
 
      # compare two adjacent elements
      if arr[j] > arr[j + 1]:
 
        # swap if elements are out-of-order
        temp = arr[j]
        arr[j] = arr[j+1]
        arr[j+1] = temp
```

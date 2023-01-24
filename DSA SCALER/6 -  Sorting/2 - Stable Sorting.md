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

### Optimized Bubble Sort Algorithm

Imagine the case where the list is already sorted. For example, our input list contains 2, 3, 4, 5 instead of 5, 3, 4, 2.
To tackle this, we can do the following:

-   Create a flag variable, called swapped.
-   The value of swapped is set to true if, during any iteration, swapping was done.
-   Else, the value of swapped is set to false.
-   After an iteration, if the value of swapped is found to be false, it means the array is sorted, and no more comparisons are required.

```python
# Optimized Bubble sort in Python
 
def bubbleSort(arr):
    
  # loop over array elements
  for i in range(len(arr)):
        
    # swapped variable initially set to false
    swapped = False
    
    for j in range(0, len(arr) - i - 1):
 
      # compare adjacent elements
      if arr[j] > arr[j + 1]:
 
        # swap if out-of-order
        temp = arr[j]
        arr[j] = arr[j+1]
        arr[j+1] = temp
  
     # set swap to true after swapping is performed
        swapped = True
          
    # array is already sorted, not need to compare further
    if not swapped:
      break
```

**Time Complexity :** O(n^2)
**Space Complexity :** O(1)

### Conclusion

-   Bubble sort is a good and simple algorithm to sort a list.
-   Good to use when memory space is limited.

## Selection Sort

-   Selection sort, also known as in-place comparison sort, is a simple sorting algorithm.
-   It works on the idea of repeatedly finding the **smallest element** and placing it at its correct sorted position. It basically selects the smallest element from an unsorted array in each iteration and places that element at the beginning of the unsorted array.
-   At any point in time, it maintains two sub-arrays for a given array :
	-   **Sorted Subarray :** The subarray that is already sorted.
	-   **Unsorted Subarray :** The remaining subarray that is unsorted.


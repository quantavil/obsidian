## Bubble Sort

Bubble sort algorithm repeatedly compares the adjacent elements and swaps them if not in order.

- In bubble sort, to sort a list of length n, we need to perform n – 1 iterations.
- After each iteration, the largest among the unsorted elements was placed at its position.
`9p>8*7I*2$S3`
### Algorithm


![[Pasted image 20230124121633.png]]
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

### Algorithm

![[Pasted image 20230124152700.png]]
1.  Start with the _first_ element. At this point, the entire list is unsorted. And the sorted sublist is empty.
2.  Iterate over the list to search for the smallest element in it.
3.  Add this element to the sorted sublist, and remove it from the unsorted sublist. In other words, swap the smallest element in the unsorted sublist with the element that is present at its correct sorted position.
4.  Repeat the above steps until all the elements from the unsorted sublist are transferred to the sorted sublist.

```python
# Selection sort in Python
 
def selectionSort(arr):
 
   # loop to iterate over the array elements
   for i in range(len(arr)):
   
       # set min_index equal to the first unsorted element
       min_index = i
 
       # iterate over unsorted sublist
       for j in range(i+1, len(arr)):
 
    #helps in finding the minimum element
           if arr[min_index] > arr[j]:
               min_index = j
           
       # swapping the minimum element with the element at min_index to place it at its correct position
     
       arr[i], arr[min_index] = arr[min_index], arr[i]
```


**Time Complexity :** O(n^2)
**Space Complexity :** O(1)

### Conclusion

-   Selection sort can be good at checking if everything is already sorted.
-   Good to use when memory space is limited.

## Insertion Sort

An insertion sort compares values in turn, starting with the second value in the list. If this value is greater than the value to the left of it, no changes are made. Otherwise, this value is repeatedly moved left until it meets a value that is less than it.

### Algorithm
![[Pasted image 20230124162005.png]]

```python
insertionSort(array)
  mark First element as sorted
  for each unsorted element E
    ‘extract’ the element E
    for j <- lastSortedIndex down to 0
      if current element j > E
        move sorted element to the right by 1
    break loop and insert E here
end InsertionSort
```

**Explanation:**

Line 2: We don’t process the first element, as it has nothing to compare against.  
Line 3: Loop from i=1 till the end, to process each element.  
Line 4: Extract the element at position i i.e. array[i]. Let it be called E.  
Line 5: To compare E with its left elements, loop j from i-1 to 0  
Line 6, 7: Compare E with the left element, if E is lesser, then move array[j] to right by 1.  
Line 8: Once we have found the position for E, place it there.


```python
#  *** PYTHON IMPLEMENTATION ***
def insertionSort(arr):
  # Start from 1 as arr[0] is always sorted
  for i in range(1, len(arr)): 
    currentElement = arr[i]
    # Move elements of arr[0..i-1], that are greater than key, 
    # to one position ahead of their current position
    j = i-1
    while j >= 0 and arr[j] > currentElement :
        arr[j + 1] = arr[j] 
        j -= 1
     # Finally place the Current element at its correct position.
    arr[j + 1] = currentElement
# Driver code to test above
arr = [9, 6, 7, 2, 5, 8]
insertionSort(arr)
for i in range(len(arr)):
  print ("% d" % arr[i])
```

**Time Complexity :** O(n^2)
**Space Complexity :** O(n)


## Quick Sort

-   Quicksort, also known as partition-exchange sort, is an in-place sorting algorithm.
-   It is a divide-and-conquer algorithm that works on the idea of selecting a pivot element and dividing the array into two subarrays around that pivot.

![quick_sort](https://scaler.com/topics/images/quick_sort.webp)

-   The array is split into two subarrays. One subarray contains the elements smaller than the pivot element, and another contains the elements greater than it.
-   At every iteration, the pivot element is placed at its correct position that it should have in the sorted array.
-   This process of selecting the pivot element and dividing the array into subarrays is carried out recursively until all the elements in the array are sorted
- [[#Example|Example]]
- [[#Time and Space complexity|Time and Space complexity]]
	- [[#Time and Space complexity#Time Complexity|Time Complexity]]
	- [[#Time and Space complexity#Space Complexity:|Space Complexity:]]
- [[#In-Place and Out-of-place Sorting:|In-Place and Out-of-place Sorting:]]
- [[#Stable and Non-Stable Sorting|Stable and Non-Stable Sorting]]
	- [[#Stable and Non-Stable Sorting#Other Characteristics of Sorting algorithms|Other Characteristics of Sorting algorithms]]

## Example

-   **Dictionary:** The dictionary stores words in alphabetical order so that searching for any word becomes easy.
-   **Telephone Book:** The telephone book stores the telephone numbers of people sorted by their names in alphabetical order, so that the names can be searched easily.
-   **E-commerce application:** While shopping through any e-commerce application like amazon or flipkart, etc. , we preferably tend to sort our items based on their price range, popularity, size, etc.

Also, the sorting algorithm's real-life usage is just miraculous! For example --

-   **Quick sort** is used for updating the real-time scores of various sports.
-   **Bubble sort** is used in TV to sort the channels based on audience viewing timings.
-   **Merge Sort** is very popularly used by databases to load a huge amount of data.

## Time and Space complexity

### Time Complexity

Time complexity in the programming world measures the approximate time taken by a piece of code, or algorithm to execute(or run) based on the size of input passed to it.

Time complexity does not give us the exact measure of time, but it gives us an overall estimation of the time taken.

The time taken mainly depends upon the number of times lines of code will iterate.

**Time complexity Notations:** These are the asymptotic notations that are used for calculating the time complexity of the sorting algorithms:

1.  **Big oh Notation, O:** It measures the upper limit of an algorithm's running time or the worst-case time complexity. It is known by *O(n)* for input size 'n'.
2.  **Omega Notation, Ω:** It measures the minimum time taken by algorithms to execute, and calculates the best case time complexity in sorting. It is known by *Ω(n)* for input size 'n'.
3.  **Theta Notation, θ:** It measures the average time taken by an algorithm to execute. Or, the lower bound and upper bound of an algorithm's running time. It is known by *θ(n)* for input size 'n'.

### Space Complexity:

Space Complexity is the total memory space required by any program for the execution of its code. It depends on the size of the data structure we are using to do our code. The sorting algorithms which take constant space are also known as the in-place sorting algorithms. If we do not use any data structure(eg. array, list etc.) then our code uses constant space. *O(1)* specifies constant space complexity. Other parameters like linear, quadratic, or exponential space complexity are similar like what we defined for our time complexity.

## In-Place and Out-of-place Sorting:
-   An **In-place algorithm** modifies the inputs, which can be a list or an array, without using any additional memory. As the algorithm runs, the input is usually overwritten by the output, so no additional space is required. Space Complexity : O(1).
- An algorithm that is not in place is called a not-in-place or out-of-place algorithm. The **Out-of-place** sorting algorithm uses extra space for sorting, which depends upon the size of the input. Space Complexity : O(n).

## Stable and Non-Stable Sorting 
**1. Stable Sorting:**

-   The Stable sorting algorithms preserve the relative order of equal elements. In other words, they maintain the relative position of similar elements after sorting.
-   If we have a key-value pair in our list, then in the case of stable sort original order of equal keys is maintained.
-   Several common sorting algorithms are stable by nature, such as Merge Sort, Timsort, Counting Sort, Insertion Sort, and Bubble Sort. We will read about them further in this tutorial.

**2. Non-Stable Sorting:**

-   In a Non-Stable sorting algorithm the ordering of the same values is not necessarily preserved/maintained after sorting.
-   Selection sort, Shell sort, Quicksort, and Heapsort may be considered an example of Non-Stable sorting algorithms.

### Other Characteristics of Sorting algorithms

1.  **Comparison Sort:** Comparison sorting algorithms are those which work by comparing each pair of adjacent elements of an iterable(such as list, array, etc.) using any comparison operator(suppose > or < or =). Some sorting algorithms are comparison sort while others are not.

For example, heap sort is a comparison sort, whereas counting sort isn’t. Bubble sort, Insertion sort, Merge sort, heap sort etc. are comparison-based sorting algorithms. Whereas, count sort, radix sort, and bucket sort are not comparison-based.

2.  **Parallelism:** Sorting algorithms are either serial or parallel. A parallel algorithm can do multiple operations at a time, whereas the serial sorting algorithms work on one operation at a time. The serial sorting algorithms work like, one operation is executed only after the previous operation is completed. We can consider the example of merge sort where two sequences say X and Y can only be merged once they are sorted. This is a kind of serial algorithm implementation. e.g. Bucket Sort
3.  **Recursive:** Some algorithms are recursive by nature, for example, the merge sort or quick sort, use the divide and conquer technique to solve the problem. This makes them more of a recursive sorting algorithm. It allows for the sorting of n elements in O(NlogN) time compared with the O(n2) efficiency of bubble sort. Hence, recursive techniques can be utilized in sorting algorithms.
4. **Sorting Categories**: Internal sorting takes place when we sort data in our RAM itself, whereas in external sorting, the data consumes extra memory to be sorted.


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
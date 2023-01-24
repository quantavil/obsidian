### Example

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
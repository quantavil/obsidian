##  What is an array?

-   Arrays are the collection of similar types of data stored at contiguous memory locations.
-   It is the simplest data structure where the data element can be accessed randomly just by using its index number.

  ## What is a linked list

A linked list is a data structure that has sequence of nodes where every node is connected to the next node by means of a reference pointer. The elements are not stored in adjacent memory locations. They are linked using pointers to form a chain. This forms a chain-like link for data storage.

-   Each node element has two parts:
 1. a data field
2.  a reference (or pointer) to the next node.

## How are linked lists more efficient than arrays 

1.  Insertion and Deletion: O(1)
2.  Dynamic Data Structure: means there is no need to give an initial size at the time of creation as it can grow and shrink at runtime by allocating and deallocating memory. Whereas, the size of an array is limited as the number of items is statically stored in the main memory.
3.  No wastage of memory

§ As the size of a linked list can grow or shrink based on the needs of the program

§ In arrays, if we declare an array of size 10 and store only 3 elements in it, then the space for 3 elements is wasted. Hence, chances of memory wastage is more in arrays.

## What is a doubly-linked list (DLL)? What are its applications.

-   This is a complex type of a linked list wherein a node has two references:

o One that connects to the next node in the sequence

o Another that connects to the previous node.

-   Use: A music playlist with next song and previous song navigation options.

## What is a stack? What are the applications of stack?

-   Stack is a linear data structure that follows LIFO (Last In First Out) approach for accessing elements.
-   Push, pop, and top (or peek) are the basic operations of a stack.

-   Uses: Check for balanced parentheses in an expression, Reverse a string

## What is a queue? What are the applications of queue?

-   A queue is a linear data structure that follows the FIFO (First In First Out) approach for accessing elements.
-   Dequeue from the queue, enqueue element to the queue, get front element of queue, and get rear element of queue are basic operations that can be performed.

## What is hashmap in data structure

1. Hashmap is a data structure that uses implementation of hash table data structure which allows access of data in constant time (O(1)) complexity if you have the key.

2. Hashing is a technique or process of mapping keys, values into the hash table by using a hash function. It is done for faster access to elements.

## Can we store a duplicate key in HashMap?

 **No**, duplicate keys cannot be inserted in HashMap. If you try to insert any entry with an existing key, then the old value would be overridden with the new value. Doing this will not change the size of HashMap.

## What is a priority queue?

 1. A priority queue is an abstract data type that is like a normal queue but has priority assigned to elements.

2. Elements with higher priority are processed before the elements with a lower priority.

3. In order to implement this, a minimum of two queues are required - one for the data and the other to store the priority.


## Sorting Algorithms

**SN**

**Sorting Algorithms**

**Description**

1

[Bubble Sort](https://www.javatpoint.com/bubble-sort)

In this algorithm we perform sorting by repeatedly moving the largest element to the highest index of the array. It comprises of comparing each element to its adjacent element and replace them accordingly.

Time Complexity: O(n^2) Space Complexity : O(log(n))

3

[Insertion Sort](https://www.javatpoint.com/insertion-sort)

In Insertion sort inserts each element of the array to its proper place.

**Step 1 –** We take the element is the first element, assume that it is already sorted.

**Step2 -** Pick the next element, and store it separately in a **key.**

**Step3 -** Now, compare the **key** with all elements in the sorted array.

**Step 4 -** Insert the value in the correct position (by shifting)

**Step 5 -** Repeat until the array is sorted.

Time Complexity: O(n^2) Space Complexity : O(1)

4

[Merge Sort](https://www.javatpoint.com/merge-sort)

Merge sort follows divide and conquer approach in which, the list is first divided into the sets of equal elements and then each half of the list is sorted by using merge sort. The sorted list is combined again to form an elementary sorted array.

 Time Complexity: O(n log(n)) Space Complexity : O(n)

5

[Quick Sort](https://www.javatpoint.com/quick-sort)

This Sorting Algorithm uses the idea of divide and conquer. It finds the element called pivot which divides the array into two halves . The we Recursively, sort two subarrays and combine them.

Time Complexity: O(n^2) Space Complexity : O(log(n))

6

[Selection Sort](https://www.javatpoint.com/selection-sort)

Selection sort finds the smallest element in the array and place it on the first place on the list, then it finds the second smallest element in the array and place it on the second place. This process continues until all the elements are moved to their correct ordering. It carries running time O(n2) which is worst than insertion sort.

Time Complexity: O(n^2) Space Complexity : O(1)
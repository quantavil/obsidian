A container is a holder object that stores a collection of other objects (its elements). They are implemented as class templates, which allows great flexibility in the types supported as elements. 

The container manages the storage space for its elements and provides member functions to access them, either directly or through iterators (reference objects with similar properties to pointers). 

**Sequence containers**

Sequence containers implement data structures that can be accessed sequentially. 

-   [**array:**](https://www.geeksforgeeks.org/array-class-c/) Static contiguous array (class template)
-   [**vector:**](https://www.geeksforgeeks.org/vector-in-cpp-stl/) Dynamic contiguous array (class template)
-   [**deque:**](https://www.geeksforgeeks.org/deque-cpp-stl/) Double-ended queue (class template)
-   [**forward_list:**](https://www.geeksforgeeks.org/forward-list-c-set-1-introduction-important-functions/) Singly-linked list (class template)
-   [**list:**](https://www.geeksforgeeks.org/list-cpp-stl/) Doubly-linked list (class template)

**Associative containers**

Associative containers implement sorted data structures that can be quickly searched (O(log n) complexity). 

-   [**Set:**](https://www.geeksforgeeks.org/set-in-cpp-stl/) Collection of unique keys, sorted by keys   
    (class template)
-   [**Map:**](https://www.geeksforgeeks.org/map-associative-containers-the-c-standard-template-library-stl/) Collection of key-value pairs, sorted by keys, keys are unique (class template).
-   [**multiset:**](https://www.geeksforgeeks.org/multiset-in-cpp-stl/) Collection of keys, sorted by keys (class template)
-   [**multimap:**](https://www.geeksforgeeks.org/multimap-associative-containers-the-c-standard-template-library-stl/) Collection of key-value pairs, sorted by keys   
    (class template)

**Unordered associative containers**

Unordered associative containers implement unsorted (hashed) data structures that can be quickly searched (O(1) amortized, O(n) worst-case complexity). 

-   [**unordered_set:**](https://www.geeksforgeeks.org/unorderd_set-stl-uses/) Collection of unique keys, hashed by keys. (class template)
-   [**unordered_map:**](https://www.geeksforgeeks.org/unordered_map-in-stl-and-its-applications/) Collection of key-value pairs, hashed by keys, keys are unique. (class template)
-   [**unordered_multiset:**](https://www.geeksforgeeks.org/unordered_multiset-and-its-uses/) Collection of keys, hashed by keys (class template)
-   [**unordered_multimap:**](https://www.geeksforgeeks.org/unordered_multimap-and-its-application/) Collection of key-value pairs, hashed by keys (class template)

**Container adapters**

Container adapters provide a different interface for sequential containers. 

-   [**stack:**](https://www.geeksforgeeks.org/stack-in-cpp-stl/) Adapts a container to provide stack (LIFO data structure) (class template).
-   [**queue:**](https://www.geeksforgeeks.org/queue-cpp-stl/) Adapts a container to provide queue (FIFO data structure) (class template).
-   [**priority_queue:**](https://www.geeksforgeeks.org/priority-queue-in-cpp-stl/) Adapts a container to provide priority queue (class template).   

[![](https://media.geeksforgeeks.org/wp-content/cdn-uploads/20200219122316/Adaptive-and-Unordered-Containers-in-C-STL.png)](https://media.geeksforgeeks.org/wp-content/cdn-uploads/20200219122316/Adaptive-and-Unordered-Containers-in-C-STL.png)

**Flowchart of Adaptive Containers and Unordered Containers**

[![](https://media.geeksforgeeks.org/wp-content/cdn-uploads/20200219122358/Sequence-and-Unordered-Containers-in-C-STL.png)](https://media.geeksforgeeks.org/wp-content/cdn-uploads/20200219122358/Sequence-and-Unordered-Containers-in-C-STL.png)

**Flowchart of Sequence containers and ordered containers**

# List



```java
Compare Types of Lists in Java

ArrayList
(extends AbstractList implements RandomAccess, Cloneable, Serializable)
- is dynamic array
- accepts duplicate elements
- is non-synchronized

LinkedList
(extends AbstractSequentialList implements Deque, Cloneable, Serializable)
- is linked list data scructure
- accepts duplicate elements
- is non-synchronized

Vector
(extends AbstractList implements RandomAccess, Cloneable, Serializable)
- growable or dynamic array of objects
- similar to array, but can grow and shrink
- synchronized


- if getting/setting more, use arrayList
   --dynamic array perofrms better for get/set
- if adding/removing more, use linkedList
   --doubly linked list better for adding removing
- if multi-thread, use Vector over arrayList
   --vector's synchronized nature better for multi-thread
- if not multi-threaded, arraylist better 
   --because it's not synchronized, thus faster
```
-   `ArrayList` is backed by an array and provides constant-time access to its elements using an index. As you mentioned, it's a good choice if you need to frequently access elements by index.
-   `LinkedList` is backed by a doubly-linked list and provides constant-time insertion and removal of elements at the beginning and end of the list. It's a good choice if you need to frequently add or remove elements from the beginning or end of the list.
-   `Vector` is similar to `ArrayList` but is synchronized, meaning that it's safe to use in a multi-threaded environment. However, its synchronization can lead to performance overhead, so it's generally not recommended to use `Vector` in single-threaded scenarios where performance is a concern.

## ArrayList

```java
package temp;

import java.util.*;

public class Main {

    public static void print(Object... objects) {
        StringBuilder sb = new StringBuilder();
        for (Object obj : objects) {
            if (obj instanceof List) {
                sb.append(((List<?>) obj).toString());
            } else if (obj instanceof Set) {
                sb.append(((Set<?>) obj).toString());
            } else if (obj instanceof Map) {
                sb.append(((Map<?, ?>) obj).toString());
            } else {
                sb.append(obj.toString());
            }
            sb.append(" ");
        }
        System.out.println(sb.toString().trim());
    }

    public static void main(String[] args) {
        List<String> list = new ArrayList<String>();
        List<String> olist = new ArrayList<>(Arrays.asList("spinach", "carrot", "broccoli", "spinach")); // [spinach,carrot,
                                                                                                         // broccoli,spinach]
        List<Integer> nlist = new ArrayList<>(Collections.nCopies(9, 0)); // [0, 0, 0, 0, 0, 0, 0, 0, 0]

        // Get a portion of the list as a new list
        List<String> clist = new ArrayList<String>(olist.subList(1, 3)); // [carrot, broccoli]

        // Convert the list to an array
        Integer[] arr = nlist.toArray(new Integer[nlist.size()]);

        // Add elements to the list
        list.add("apple"); // [apple]
        list.add("banana"); // [apple, banana]
        list.add("cherry"); // apple, banana, cherry

        // Add an element at a specific index
        list.add(1, "Mango"); // [apple, Mango, banana, cherry]

        // Get the size of the list
        int size = list.size(); // 4

        // Get an element at a specific index
        String element = list.get(1); // Mango

        // Remove an element from the list
        list.remove("banana"); // [apple, Mango, cherry]

        // Replace an element at a specific index
        list.set(2, "Tomato"); // [apple, Mango, Tomato]

        // Check if an element is in the list
        boolean contains = list.contains("apple"); // true

        // Check if the list is empty
        boolean isEmpty = list.isEmpty(); // false

        // Get the index of a specific element
        int index = olist.indexOf("spinach"); // 0

        // Get the last index of a specific element
        int lastIndex = olist.lastIndexOf("spinach"); // 3

        // Add all elements from another collection to the list
        list.addAll(olist); // [apple, Mango, Tomato, spinach, carrot, broccoli, spinach]

        // Remove all elements from the list that do not match a specified condition
        list.removeIf(str -> str.length() < 6); // [Tomato, spinach, carrot, broccoli, spinach]
        print(list);

        // count the the number of occurences
        Collections.frequency(list, "spinach"); // 2

        // Sort the elements in the list
        Collections.sort(list); // [Tomato, spinach, carrot, broccoli, spinach]
        print(list);

        // Reverse the order of the elements in the list
        Collections.reverse(list); // [spinach, spinach, carrot, broccoli, Tomato]

		// Remove all elements from the list that are in another collection 
		list.removeAll(olist);
		
		// Clear all elements from the list 
		list.clear();

    }

}
```

## Sets

Sets contain elements uniquely. (The same element cannot be in the set more than once.)

-   `HashSet`: does not retain order
-   `LinkedHashSet`: keeps the order of insertion
-   `TreeSet`: Sorts in natural order Set operations like intersection, difference are implemented for sets (`retainAll`, `removeAll`).


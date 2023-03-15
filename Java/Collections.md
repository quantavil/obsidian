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

### HashSet

```java
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

        Set<String> set = new HashSet<>();
        Set<String> oSet = new HashSet<>(Arrays.asList("orange", "banana", "watermelon", "apple"));
        // Converting the HashSet to a TreeSet (a sorted set)
        TreeSet<String> sortedSet = new TreeSet<>(set);
        
        // Add elements to the set
        set.add("apple");
        set.add("banana");
        set.add("cherry");
        set.add("banana"); // Adding a duplicate element will be ignored

        boolean containsApple = set.contains("apple"); // check if the HashSet contains an element

        int setSize = set.size(); // get the size of the HashSet
        boolean isSetEmpty = set.isEmpty(); // check if the HashSet is empty
        boolean isEqual = set.equals(oSet); // False

		//*ALL OF BELOW METHODS ARE INPLACE , Therefore set is taken reference everytime  *//
		
        // Removing an element from the HashSet if it satisfies a condition
        set.removeIf(fruit -> fruit.startsWith("a")); // [banana, cherry]

        // Retaining only the elements that are in both the HashSet and another collection
        set.retainAll(oSet); // {banana, apple}

        // Adding all elements of another collection to the HashSet
        set.addAll(oSet); // {banana, orange, apple, cherry, watermelon}

        // Removing all elements that are in another collection from the HashSet
        set.removeAll(oSet); // {cherry}

        set.clear(); // remove all elements from the HashSet

    }
}

```

### TreeSet

`TreeSet` is another implementation of the `Set` interface in Java that stores elements in a sorted order. Here are some additional `TreeSet` methods:

```java
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
        TreeSet<Integer> set = new TreeSet<>(); // initialize a new TreeSet

        set.add(10); // add an element to the TreeSet
        set.add(20);
        set.add(30); //output: [10, 20, 30]


        // Getting the first (lowest) element in the TreeSet
        int firstElement = set.first(); //10

        // Getting the last (highest) element in the TreeSet
        int lastElement = set.last(); // 30

        // Getting a view of the TreeSet with elements less than a specified value
        Set<Integer> lessThanTwenty = set.headSet(20); // [10]

        // Getting a view of the TreeSet with elements greater than or equal to a
        // specified value
        Set<Integer> greaterThanOrEqualToTwenty = set.tailSet(20); // [20, 30]

        // Getting a view of the TreeSet with elements within a specified range
        // (inclusive)
        Set<Integer> betweenTwentyAndThirty = set.subSet(20, 30); // [20]


        // Creating a shallow copy of the TreeSet
        TreeSet<Integer> setCopy = new TreeSet<>(set);

        // Removing the first (lowest) element in the TreeSet
        int removedElement = set.pollFirst();

        System.out.println(set); // output: [20, 30]
        System.out.println(removedElement); // output: 10

        // Removing the last (highest) element in the TreeSet
        int removedElement2 = set.pollLast();

        System.out.println(set); // output: [20]
        System.out.println(removedElement2); // output: 30

        // Checking if the TreeSet contains an element greater than or equal to a
        // specified value
        boolean containsTwenty = set.ceiling(20) != null; // true

    }
}

```

## Map

Maps store key-value pairs. Implement the `Map` interface.

-   `HashMap`: Does not maintain order.
-   `LinkedMap`: Behind this there is a doubly linked list. This maintains the order.
-   `TreeMap`: Will sort the keys in natural order.

### HashMap

```java
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

        // Create a new HashMap
        HashMap<String, Integer> hashMap = new HashMap<>();
        
        // Add some key-value pairs to the HashMap
        hashMap.put("apple", 1);
        hashMap.put("banana", 2);
        hashMap.put("cherry", 3);

        // Retrieve the value associated with a key
        int value = hashMap.get("banana"); // 2

        // Check if a key is present in the HashMap
        boolean containsKey = hashMap.containsKey("apple"); // true

        // Check if a value is present in the HashMap
        boolean containsValue = hashMap.containsValue(3); // true

        // Remove a key-value pair from the HashMap
        hashMap.remove("banana"); // {apple=1, cherry=3}

        // Get a set of all keys in the HashMap
        Set<String> keySet = hashMap.keySet(); // [apple, cherry]

        // Get a collection of all values in the HashMap
        Collection<Integer> values = hashMap.values(); // [1, 3]

        // Get the number of key-value pairs in the HashMap
        int size = hashMap.size(); // 2

        // Remove all key-value pairs from the HashMap
        hashMap.clear(); // {}

        HashMap<String,Integer> oHashMap = new HashMap<String,Integer>() {{ put("apple", 1); put("banana", 2); put("cherry", 3);}}; // {cherry=3, apple=1, banana=2}
        
        // Replace the value associated with a key
        oHashMap.replace("banana", 4); // {apple=1, banana=4, cherry=3}

        // Replace the value associated with a key only if it matches a given value
        oHashMap.replace("banana", 4, 5); // {apple=1, banana=5, cherry=3}

        // Add a key-value pair to the HashMap only if the key is not already present
        oHashMap.putIfAbsent("durian", 6); // {apple=1, banana=5, cherry=3, durian=6}

        // Get the value associated with a key, or a default value if the key is not present
        int val = hashMap.getOrDefault("elderberry", 7);  // 7

        // Compute a new value for a key using a given function
        oHashMap.compute("cherry", (k, v) -> v * 3); // {banana=7, apple=1, cherry=9, durian=6}

        // Compute a new value for a key only if it is present using a given function
        oHashMap.computeIfPresent("durian", (k, v) -> v * 3); // {banana=7, apple=1, cherry=9, durian=18}

        // Compute a new value for a key only if it is not present using a given
        // function
        oHashMap.computeIfAbsent("elderberry", k -> k.length()); // {banana=7, apple=1, cherry=9, elderberry=10, durian=18}

        //Merge maps
        oHashMap.putAll(hashMap);
    }
}
```


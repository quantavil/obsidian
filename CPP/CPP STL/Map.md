Maps in C++ are container structures that store elements in key-value pairs. This means that for every unique key, there is a data value mapped to it, that can be easily accessed if we know the key. This is why every key has to be unique, and no two keys can be the same(but the values associated to keys can be the same).

Maps in C++ store the key-value pairs in sorted order by default so that the search for any key-value pair can be very quick.

![[map-define.webp]]

**SYNTAX :**

```cpp
map <key_dataType, value_dataType> mapName;
```

**INITIALIZATION :**

```cpp
    map<string, int> mp;

    // Assign values to the map

    mp["Asia"] = 1; // Inserts key = "Asia" with value = 1
    mp["Europe"] = 2; // Inserts key = "Europe" with value = 2
    mp["Australia"] = 3; // Inserts key = "Australia" with value = 3
    mp["Antarctica"] = 4 ; // Inserts key = "Antarctica" with value = 4

```

## Iterators

1.   [begin()](https://www.geeksforgeeks.org/mapbegin-end-c-stl/) – Returns an iterator to the first element in the map.
2.  [end()](https://www.geeksforgeeks.org/mapbegin-end-c-stl/) – Returns an iterator to the theoretical element that follows the last element in the map.

## Capacity

-   [size()](https://www.geeksforgeeks.org/mapsize-c-stl/) – Returns the number of elements in the map.
-   [max_size()](https://www.geeksforgeeks.org/map-max_size-in-c-stl/) – Returns the maximum number of elements that the map can hold.
-   [empty()](https://www.geeksforgeeks.org/mapempty-c-stl/) – Returns whether the map is empty.

## Element access

1. [map::operator[]](https://www.geeksforgeeks.org/map-operator-cpp-stl/) - This operator is used to reference the element present at the position given inside the operator.
2. [map::at()](https://www.geeksforgeeks.org/mapat-mapswap-c-stl/) - at() function is used to return the reference to the element associated with the key k.

```cpp
map<int,string> mymap;
	// mapping integers to strings
	mymap[2] = "This";
	mymap[3] = "is";
	mymap[4] = "Bot";
	mymap[5] = "Fish";
	
	// using operator[] to print string
	// mapped to integer 4
	
cout << mymap[4]; // Bot
cout << map1.at(2); // This
```
## Modifiers

1. [pair insert(keyvalue, mapvalue)](https://www.geeksforgeeks.org/map-insert-in-c-stl/) – Insert elements with a particular key in the map container –> O(log n)
2. [erase(iterator position)](https://www.geeksforgeeks.org/map-erase-function-in-c-stl/) – Removes the element at the position pointed by the iterator.
4. [clear()](https://www.geeksforgeeks.org/mapclear-c-stl/) – Removes all the elements from the map.
5. [map::swap()](https://www.geeksforgeeks.org/mapat-mapswap-c-stl/) - swap() function is used to exchange the contents of two maps but the maps must be of the same type, although sizes may differ.

```cpp
// initialize container
map<int, int> mp;

// insert elements in random order
mp.insert({ 2, 30 }); // {2:30}
mp.insert({ 1, 40 }); // {1:40, 2:30}
mp.insert({ 4, 60 });  // {1:40, 2:30, 4:60}

// does not inserts key 2 with element 20
mp.insert({ 2, 20 }); // {1:40, 2:30, 4:60}

// inserts {3, 70} starting the search from position where 2 is present
auto it = mp.find(2);
mp.insert(it, { 3, 70 });  // {1:40, 2:30, 3:70, 4:60}

// function to erase given keys
mp.erase(1); // {2:30, 3:70, 4:60}
mp.erase(2); // { 3:70, 4:60}

// function to erase given position
auto it = mp.find(4);
mp.erase(it); // { 3:70, 4:60}

// Swap elements of queues
swap(map1, map2); 
/* OR */
map1.swap(map2)

```
## Operations

1. [map find()](https://www.geeksforgeeks.org/map-find-function-in-c-stl/) - Returns an iterator to the element with key-value ‘g’ in the map if found, else returns the iterator to end.
2. [map:: count()](https://www.geeksforgeeks.org/map-count-function-in-c-stl/) - Returns the number of matches to element with key-value ‘g’ in the map. –> O(log n)
3. [map lower_bound()](https://www.geeksforgeeks.org/map-lower_bound-function-in-c-stl/) - Returns an iterator to the first element that is equivalent to the mapped value with key-value ‘g’ or definitely will not go before the element with key-value ‘g’ in the map –> O(log n)
4. [map upper_bound()](https://www.geeksforgeeks.org/map-upper_bound-function-in-c-stl/) - Returns an iterator to the first element that is equivalent to mapped value with key-value ‘g’ or definitely will go after the element with key-value ‘g’ in the map
5. [map equal_range()](https://www.geeksforgeeks.org/map-equal_range-in-c-stl/) - Returns an iterator of pairs. The pair refers to the bounds of a range that includes all the elements in the container which have a key equivalent to k.

```cpp

```
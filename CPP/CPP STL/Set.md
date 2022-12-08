 Sets are a type of associative container in which each element has to be unique because the value of the element identifies it. The values are stored in a specific sorted order i.e. either ascending or descending.

**SYNTAX :**
```cpp
set<datatype> setname;
```

**INITIALIZATION :**

```cpp
set<int> val; // defining an empty set
set<int> val = {6, 10, 5, 1}; // defining a set with values
set<int> s2(s1);
```


## **Properties:**

1.  **Storing order –** The set stores the elements in **sorted** order.
2.  **Values Characteristics** – All the elements in a set have **unique values**.
3.  **Values Nature** – The value of the element cannot be modified once it is added to the set, though it is possible to remove and then add the modified value of that element. Thus, the values are **immutable**.
4.  **Search Technique** – Sets follow the **Binary search tree** implementation.
5.  **Arranging order –** The values in a set are **unindexed**.


## C++ Set STL Member Functions

### Iterators 

1. [begin()](https://www.geeksforgeeks.org/setbegin-setend-c-stl/) - Returns an iterator to the first element in the set.
2. [end()](https://www.geeksforgeeks.org/setbegin-setend-c-stl/) - Returns an iterator to the theoretical element that follows the last element in the set.
3. [~~rbegin()~~](https://www.geeksforgeeks.org/setrbegin-and-setrend-in-c-stl/)- Returns a reverse iterator pointing to the last element in the container.
4. [~~rend()~~](https://www.geeksforgeeks.org/setrbegin-and-setrend-in-c-stl/)Returns a reverse iterator pointing to the theoretical element right before the first element in the set container.
5. [~~crbegin()~~](https://www.geeksforgeeks.org/set-crbegin-and-crend-function-in-c-stl/)Returns a constant iterator pointing to the last element in the container.
6. [~~crend()~~](https://www.geeksforgeeks.org/set-crbegin-and-crend-function-in-c-stl/)Returns a constant iterator pointing to the position just before the first element in the container.
7. [~~cbegin()~~](https://www.geeksforgeeks.org/set-cbegin-and-cend-function-in-c-stl/)Returns a constant iterator pointing to the first element in the container.
8. [~~cend()~~](https://www.geeksforgeeks.org/set-cbegin-and-cend-function-in-c-stl/)Returns a constant iterator pointing to the position past the last element in the container.

**EXAMPLE :**

```cpp
set<int> s = {6, 10, 5, 1}; 
for (auto it = s.begin(); it != s.end(); it++) // 1 5 6 10
		cout << *it << " ";
for (auto it = s1.rbegin(); it != s1.rend(); it++) // 10 6 5 1
	cout << *it << " ";
for (auto it = s.crbegin(); it != s.crend(); it++) // 10 6 5 1
	cout << *it << " ";
for (auto it = s.cbegin(); it != s.cend(); it++) // 1 5 6 10
	cout << *it << " ";
```

### Capacity

[size()](https://www.geeksforgeeks.org/setsize-c-stl/) - Returns the number of elements in the set.
[max_size()](https://www.geeksforgeeks.org/set-max_size-function-in-c-stl/) - Returns the maximum number of elements that the set can hold.
[empty()](https://www.geeksforgeeks.org/setempty-c-stl/) - Returns whether the set is empty.

```cpp
set<int> s = {6, 10, 5, 1, 13}; 
cout << "set1 size: " << set1.size(); // 5
cout << s2.max_size(); // 461168601842738790

if (myset.empty()) 
    cout << "True";
else 
    cout << "False";
// True

```

### Modifier

[insert(const g)](https://www.geeksforgeeks.org/set-insert-function-in-c-stl/) - Adds a new element ‘g’ to the set.
[iterator insert (iterator position, const g)](https://www.geeksforgeeks.org/set-insert-function-in-c-stl/) - Adds a new element ‘g’ at the position pointed by the iterator.
[swap()](https://www.geeksforgeeks.org/setswap-c-stl/) - This function is used to exchange the contents of two sets but the sets must be of the same type, although sizes may differ.
[erase(const g)](https://www.geeksforgeeks.org/seterase-c-stl/) - Removes the value ‘g’ from the set.
[erase(iterator position)](https://www.geeksforgeeks.org/seterase-c-stl/) - Removes the element at the position pointed by the iterator.
[clear()](https://www.geeksforgeeks.org/setclear-c-stl/) - Removes all the elements from the set.
[~~emplace()~~](https://www.geeksforgeeks.org/setemplace-c-stl/) - This function is used to insert a new element into the set container, only if the element to be inserted is unique and does not already exist in the set.
[~~emplace_hint()~~](https://www.geeksforgeeks.org/set-emplace_hint-function-in-c-stl/) - Returns an iterator pointing to the position where the insertion is done. If the element passed in the parameter already exists, then it returns an iterator pointing to the position where the existing element is.

**EXAMPLE :**

```cpp
set<int> s {6, 10 , 11, 15 ,13};

set<int> s;
s.insert(1); // 1, 6, 10 , 11, 15 ,13
   
set<int> s1;
	s1.insert(s.find(10), s.end()); // 10 11 15 13

set<int> set1{ 1, 2, 3, 4 };
set<int> set2{ 5, 6, 7, 8 };
	set1.swap(set2); // set2 --> { 1, 2, 3, 4 }
					 // set1 --> { 5, 6, 7, 8 }

myset.erase(2); //  6, 10, 13, 15

myset.erase(1, 3); // 10 , 13

set.clear(); // 

myset.emplace(1); // 1, 6, 10 , 11, 13 ,15

s.emplace_hint(s.begin(), 1); // 1, 6, 10 , 11, 15 ,13
```

### Operations

[find(const g)](https://www.geeksforgeeks.org/set-find-function-in-c-stl/) - Returns an iterator to the element ‘g’ in the set if found, else returns the iterator to end.
[count(const g)](https://www.geeksforgeeks.org/set-count-function-in-c-stl/) - Returns 1 or 0 based on whether the element ‘g’ is present in the set or not.
[lower_bound(const g)](https://www.geeksforgeeks.org/set-lower_bound-function-in-c-stl/) - Returns an iterator to the first element that is equivalent to ‘g’ or definitely will not go before the element ‘g’ in the set.
[upper_bound(const g)](https://www.geeksforgeeks.org/set-upper_bound-function-in-c-stl/) - Returns an iterator to the first element that will go after the element ‘g’ in the set.
[equal_range()](https://www.geeksforgeeks.org/set-equal_range-function-in-c-stl/) - The function returns an iterator of pairs. (key_comp). The pair refers to the range that includes all the elements in the container which have a key equivalent to k

```cpp

  set<int> s ={12,43,234,65,34,54,3,2,87,213,76,454};

  set<int>::iterator it;

  it = s.find(54);
  cout << "The iterator is pointing to - " << * it << "\n"; // 54

  if (s.count(234)) {
    cout << "True" << "\n"; // True
  } else {
    cout << "False" << "\n";
  }

  it = s.lower_bound(10);
  cout << "The lower_bound of 10 is " << * it << "\n"; // 12

  it = s.upper_bound(12);
  cout << "The upper_bound of 12 is " << * it << "\n"; // 34


```
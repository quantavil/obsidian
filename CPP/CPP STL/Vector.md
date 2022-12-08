- [[#What is Vector ?|What is Vector ?]]
- [[#C++ Vector STL Member Functions|C++ Vector STL Member Functions]]
	- [[#C++ Vector STL Member Functions#Iterators|Iterators]]
	- [[#C++ Vector STL Member Functions#Capacity|Capacity]]
	- [[#C++ Vector STL Member Functions#Element access|Element access]]
	- [[#C++ Vector STL Member Functions#Modifiers|Modifiers]]
- [[#Vector of Vector|Vector of Vector]]
- [[#Array of vectors|Array of vectors]]
- [[#Vector of Pairs|Vector of Pairs]]
-   [Ways to copy a vector in C++](https://www.geeksforgeeks.org/ways-copy-vector-c/ "Permalink to Ways to copy a vector in C++")
-   [Sorting 2D Vector in C++ | Set 3 (By number of columns)](https://www.geeksforgeeks.org/sorting-2d-vector-c-set-3-number-columns/ "Permalink to Sorting 2D Vector in C++ | Set 3 (By number of columns)"),[(Sort in descending order by first and second)](https://www.geeksforgeeks.org/sorting-vector-of-pairs-in-c-set-2-sort-in-descending-order-by-first-and-second/ "Permalink to Sorting Vector of Pairs in C++ | Set 2 (Sort in descending order by first and second)")
-   [Sorting 2D Vector in C++ | Set 2 (In descending order by row and column)](https://www.geeksforgeeks.org/sorting-2d-vector-in-c-set-2-in-descending-order-by-row-and-column/ "Permalink to Sorting 2D Vector in C++ | Set 2 (In descending order by row and column)")
-   [Sorting 2D Vector in C++ | Set 1 (By row and column)](https://www.geeksforgeeks.org/sorting-2d-vector-in-c-set-1-by-row-and-column/ "Permalink to Sorting 2D Vector in C++ | Set 1 (By row and column)"), [(Sort by first and second](https://www.geeksforgeeks.org/sorting-vector-of-pairs-in-c-set-1-sort-by-first-and-second/ "Permalink to Sorting Vector of Pairs in C++ | Set 1 (Sort by first and second)")

Vectors are containers representing arrays used to store elements of the same data type but the size of a vector grows and shrinks dynamically, that is, it can change its size during runtime. The elements of a vector are placed in contiguous memory locations so that they can be accessed and traversed using iterators.

## What is Vector ?

Vector is a linear data structure that stores similar type objects. It is a template class in C++ STL(standard template library). A vector is implemented as an array which is free to add elements even beyond its predefined size
![[Vector-in-C.webp]]
![[What-is-Vetor.webp]]

**SYNTAX :**
```cpp
vector<Data_Type> vector_name; // initialisation
vector<Data_Type> vector_name(size); // initialisation with size
vector<Data_Type> vector_name(size, value); // initialisation with size and value

vector<vector<Data_type>> vector_name; //2D vector
```

**INITIALIZATION :**

```cpp
// CODE
vector<int> a = { 1, 2, 3, 4, 5 }; //1 2 3 4 5 vector is created
vector<int> b(5); // b = {0, 0, 0, 0, 0}
vector<int> c(5, -1); // c = {-1, -1, -1, -1, -1} vector is created
```


## C++ Vector STL Member Functions

### Iterators 

1.  [begin()](https://www.geeksforgeeks.org/vectorbegin-vectorend-c-stl/) – Returns an iterator pointing to the first element in the vector
2.  [end()](https://www.geeksforgeeks.org/vectorbegin-vectorend-c-stl/) – Returns an iterator pointing to the theoretical element that follows the last element in the vector
3.  [~~rbegin()~~](https://www.geeksforgeeks.org/vector-rbegin-and-rend-function-in-c-stl/) – Returns a reverse iterator pointing to the last element in the vector (reverse beginning). It moves from last to first element
4.  [~~rend()~~](https://www.geeksforgeeks.org/vector-rbegin-and-rend-function-in-c-stl/) – Returns a reverse iterator pointing to the theoretical element preceding the first element in the vector (considered as reverse end)
5.  [~~cbegin()~~](https://www.geeksforgeeks.org/vector-cbegin-vector-cend-c-stl/) – Returns a constant iterator pointing to the first element in the vector.
6.  [~~cend()~~](https://www.geeksforgeeks.org/vector-cbegin-vector-cend-c-stl/) – Returns a constant iterator pointing to the theoretical element that follows the last element in the vector.
7.  [~~crbegin()~~](https://www.geeksforgeeks.org/vectorcrend-vectorcrbegin-examples/) – Returns a constant reverse iterator pointing to the last element in the vector (reverse beginning). It moves from last to first element
8.  [~~crend()~~](https://www.geeksforgeeks.org/vectorcrend-vectorcrbegin-examples/) – Returns a constant reverse iterator pointing to the theoretical element preceding the first element in the vector (considered as reverse end)


**EXAMPLE  :**

```cpp
[[include]] <iostream>
[[include]] <vector>

vector<int> g1 {1 ,2 ,3 ,4 ,5};
for (auto i = g1.begin(); i != g1.end(); ++i)
	cout << *i << " "; // 1 2 3 4 5

for (auto i = g1.cbegin(); i != g1.cend(); ++i)
	cout << *i << " "; // 1 2 3 4 5

for (auto ir = g1.rbegin(); ir != g1.rend(); ++ir)
	cout << *ir << " "; // 5 4 3 2 1

for (auto ir = g1.crbegin(); ir != g1.crend(); ++ir)
	cout << *ir << " "; // 5 4 3 2 1
```

### Capacity

1.  [size()](https://www.geeksforgeeks.org/vectorempty-vectorsize-c-stl/) – Returns the number of elements in the vector.
2.  [max_size()](https://www.geeksforgeeks.org/vector-max_size-function-in-c-stl/) – Returns the maximum number of elements that the vector can hold.
3.  [capacity()](https://www.geeksforgeeks.org/vector-capacity-function-in-c-stl/) – Returns the size of the storage space currently allocated to the vector expressed as number of elements.
4.  [resize(n)](https://www.geeksforgeeks.org/vector-resize-c-stl/) – Resizes the container so that it contains ‘n’ elements.
5.  [empty()](https://www.geeksforgeeks.org/vectorempty-vectorsize-c-stl/) – Returns whether the container is empty.
6.  [~~shrink_to_fit()~~](https://www.geeksforgeeks.org/vector-shrink_to_fit-function-in-c-stl/) – Reduces the capacity of the container to fit its size and destroys all elements beyond the capacity.
7.  [~~reserve()~~](https://www.geeksforgeeks.org/using-stdvectorreserve-whenever-possible/) – Requests that the vector capacity be at least enough to contain n elements.

**EXAMPLE :**

```cpp

vector<int> g1 {1 ,2 ,3 ,4 ,5};

cout << "Size : " << g1.size(); // Size : 5
cout << "\nCapacity : " << g1.capacity(); // Capacity : 8
cout << "\nMax_Size : " << g1.max_size(); // Max_Size : 4611686018427387903

// resizes the vector size to 4
g1.resize(4); 
cout << "\nSize : " << g1.size(); // Size : 4

// checks if the vector is empty or not
if (g1.empty() == false)
	cout << "\nVector is not empty";
else
	cout << "\nVector is empty";
// Vector is not empty


// Shrinks the vector
g1.shrink_to_fit();
cout << "\nVector elements are: ";
for (auto it = g1.begin(); it != g1.end(); it++)
	cout << *it << " "; // Vector elements are: 1 2 3 4 5


```

### Element access

1.  [reference operator [g]](https://www.geeksforgeeks.org/vectoroperator-vectoroperator-c-stl/) – Returns a reference to the element at position ‘g’ in the vector
2.  [at(g)](https://www.geeksforgeeks.org/vectorat-vectorswap-c-stl/) – Returns a reference to the element at position ‘g’ in the vector
3.  [front()](https://www.geeksforgeeks.org/vectorfront-vectorback-c-stl/) – Returns a reference to the first element in the vector
4.  [back()](https://www.geeksforgeeks.org/vectorfront-vectorback-c-stl/) – Returns a reference to the last element in the vector
5.  [data()](https://www.geeksforgeeks.org/vector-data-function-in-c-stl/) – Returns a direct pointer to the memory array used internally by the vector to store its owned elements.

**EXAMPLE :**

```cpp
vector<int> g1 {10,20,30,40,50,60,70,80,90,100};
cout << "\nReference operator [g] : g1[2] = " << g1[2]; // 30
cout << "\nat : g1.at(4) = " << g1.at(4); // 50
cout << "\nfront() : g1.front() = " << g1.front(); // 10
cout << "\nback() : g1.back() = " << g1.back(); // 100

// pointer to the first element
int* pos = g1.data();
cout << "\nThe first element is " << *pos; // 10
```

### Modifiers

1.  [assign()](https://www.geeksforgeeks.org/vector-assign-in-c-stl/) – It assigns new value to the vector elements by replacing old ones
2.  [push_back()](https://www.geeksforgeeks.org/vectorpush_back-vectorpop_back-c-stl/) – It push the elements into a vector from the back
3.  [pop_back()](https://www.geeksforgeeks.org/vectorpush_back-vectorpop_back-c-stl/) – It is used to pop or remove elements from a vector from the back.
4.  [insert()](https://www.geeksforgeeks.org/vector-insert-function-in-c-stl/) – It inserts new elements before the element at the specified position
5.  [erase()](https://www.geeksforgeeks.org/vectorclear-vectorerase-c-stl/) – It is used to remove elements from a container from the specified position or range.
6.  [swap()](https://www.geeksforgeeks.org/vectorat-vectorswap-c-stl/) – It is used to swap the contents of one vector with another vector of same type. Sizes may differ.
7.  [clear()](https://www.geeksforgeeks.org/vectorclear-vectorerase-c-stl/) – It is used to remove all the elements of the vector container
8.  [~~emplace()~~](https://www.geeksforgeeks.org/vector-emplace-function-in-c-stl/) – It extends the container by inserting new element at position
9.  [~~emplace_back()~~](https://www.geeksforgeeks.org/vectoremplace_back-c-stl/) – It is used to insert a new element into the vector container, the new element is added to the end of the vector
as
**EXAMPLE :**

```cpp
// Assign vector
vector<int> v {2,5,7,11}; 

// fill the array with 10 five times
v.assign(5, 10); // 10 10 10 10 10

// inserts 15 to the last position
v.push_back(15); // 2 5 7 11 15

// removes last element
v.pop_back(); // 2 5 7



// inserts 5 at the beginning
v.insert(v.begin(), 5); // 5 2 5 7 11

// removes the first element
v.erase(v.begin()); // 5 7 11

// inserts at the beginning
v.emplace(v.begin(), 17); // 17 2 5 7 11


// Inserts 20 at the end
v.emplace_back(20); // 2 5 7 11 20

// erases the vector
v.clear(); //
```


## Vector of Vector

**Vector of Vectors** is a [two-dimensional vector](https://www.geeksforgeeks.org/2d-vector-in-cpp-with-user-defined-size/) with a variable number of rows where each row is vector. Each index of vector stores a vector which can be traversed and accessed using [iterators](https://www.geeksforgeeks.org/iterators-c-stl/). 

**SYNTAX :**
```cpp
vector<vector<data_type>> vec;
```

**INITIALIZATION :**
```cpp
vector<vector<int> > vec;
vector<vector<int>> vec{ { 1, 2, 3 }, 
                         { 4, 5, 6 }, 
                         { 7, 8, 9, 4 } }; 
```


**Insertion in Vector of Vectors**

```cpp
v2 = {1, 2, 3}
v1.push_back(v2); // {{1,2,3}}
```

```cpp
v2 = {4, 5, 6}
v1.push_back(v2); //  {{1, 2, 3}, {4, 5, 6}}
```


**Removal or Deletion in a Vector of Vectors**

```cpp
v = {{ 1, 2, 3 }, { 4, 5, 6 }, { 7, 8, 9 }}

// removing element from last row
v[2].pop_back() // {{ 1, 2, 3 }, { 4, 5, 6 }, { 7, 8 }}
```

```cpp
// removing element from second last row
v[1].pop_back() // { { 1, 2, 3 }, { 4, 5 }, { 7, 8 } }
```


**Traversal of a Vector of Vectors**

```cpp
for i in [0, n)
{
    for (iterator it = v[i].begin();
         it != v[i].end(); it++) 
   {
        // Operations to be done
        // For example to print
        print(*it)
    }
}
```

## Array of vectors

**SYNTAX :**
```cpp
vector <data_type> V[size];
```

**EXAMPLE  :**

```cpp
vector <int> A[5];
```

```cpp
// C++ program to illustrate
// array of vectors

[[include]] <iostream>
[[include]] <vector>
using namespace std;

// Declaring array of vectors
// globally
vector<int> v[5];

// Function for inserting elements
// in array of vectors
void insertionInArrayOfVectors()
{

	for (int i = 0; i < 5; i++) {

		// Inserting elements at every
		// row i using push_back()
		// function in vector
		for (int j = i + 1; j < 5; j++) {
			v[i].push_back(j);
		}
	}
}

// Function to print elements in array
// of vectors
void printElements()
{

	// Traversing of vectors v to print
	// elements stored in it
	for (int i = 0; i < 5; i++) {

		cout << "Elements at index "
			<< i << ": ";

		// Displaying element at each column,
		// begin() is the starting iterator,
		// end() is the ending iterator
		for (auto it = v[i].begin();
			it != v[i].end(); it++) {

			// (*it) is used to get the
			// value at iterator is
			// pointing
			cout << *it << ' ';
		}
		cout << endl;
	}
}

// Function to illustrate array
// of vectors
void arrayOfVectors()
{
	// Inserting elements in array
	// of vectors
	insertionInArrayOfVectors();

	// Print elements stored in array
	// of vectors
	printElements();
}

// Driver code
int main()
{
	arrayOfVectors();
	return 0;
}

```

## Vector of Pairs

**SYNTAX :**
```cpp
vector< pair <data_type,data_type> > vect;
```

```cpp
// C++ program to demonstrate vector of pairs
[[include]]<bits/stdc++.h>
using namespace std;

int main()
{
	//declaring vector of pairs
	vector< pair <int,int> > vect;

	// initialising 1st and 2nd element of
	// pairs with array values
	int arr[] = {10, 20, 5, 40 };
	int arr1[] = {30, 60, 20, 50};
	int n = sizeof(arr)/sizeof(arr[0]);

	// Entering values in vector of pairs
	for (int i=0; i<n; i++)
		vect.push_back( make_pair(arr[i],arr1[i]) );

	// Printing the vector
	for (int i=0; i<n; i++)
	{
		// "first" and "second" are used to access
		// 1st and 2nd element of pair respectively
		cout << vect[i].first << " "
			<< vect[i].second << endl;
	}

	return 0;
}
```

**Case 1 : Sorting the vector elements on the basis of first element of pairs in ascending order.**

```cpp
// C++ program to demonstrate sorting in
// vector of pair according to 1st element
// of pair
[[include]]<bits/stdc++.h>
using namespace std;

int main()
{
	// Declaring vector of pairs
	vector< pair <int,int> > vect;

	// Initializing 1st and 2nd element of
	// pairs with array values
	int arr[] = {10, 20, 5, 40 };
	int arr1[] = {30, 60, 20, 50};
	int n = sizeof(arr)/sizeof(arr[0]);

	// Entering values in vector of pairs
	for (int i=0; i<n; i++)
		vect.push_back( make_pair(arr[i],arr1[i]) );

	// Printing the original vector(before sort())
	cout << "The vector before sort operation is:\n" ;
	for (int i=0; i<n; i++)
	{
		// "first" and "second" are used to access
		// 1st and 2nd element of pair respectively
		cout << vect[i].first << " "
			<< vect[i].second << endl;

	}

	// Using simple sort() function to sort
	sort(vect.begin(), vect.end());

	// Printing the sorted vector(after using sort())
	cout << "The vector after sort operation is:\n" ;
	for (int i=0; i<n; i++)
	{
		// "first" and "second" are used to access
		// 1st and 2nd element of pair respectively
		cout << vect[i].first << " "
			<< vect[i].second << endl;
	}

	return 0;
}
```

**Case 2 : Sorting the vector elements on the basis of second element of pairs in ascending order.**

```cpp
// C++ program to demonstrate sorting in vector
// of pair according to 2nd element of pair
[[include]]<bits/stdc++.h>
using namespace std;

// Driver function to sort the vector elements
// by second element of pairs
bool sortbysec(const pair<int,int> &a,
			const pair<int,int> &b)
{
	return (a.second < b.second);
}

int main()
{
	// declaring vector of pairs
	vector< pair <int, int> > vect;

	// Initialising 1st and 2nd element of pairs
	// with array values
	int arr[] = {10, 20, 5, 40 };
	int arr1[] = {30, 60, 20, 50};
	int n = sizeof(arr)/sizeof(arr[0]);

	// Entering values in vector of pairs
	for (int i=0; i<n; i++)
		vect.push_back( make_pair(arr[i],arr1[i]) );

	// Printing the original vector(before sort())
	cout << "The vector before sort operation is:\n" ;
	for (int i=0; i<n; i++)
	{
		// "first" and "second" are used to access
		// 1st and 2nd element of pair respectively
		cout << vect[i].first << " "
			<< vect[i].second << endl;

	}

	// Using sort() function to sort by 2nd element
	// of pair
	sort(vect.begin(), vect.end(), sortbysec);

	// Printing the sorted vector(after using sort())
	cout << "The vector after sort operation is:\n" ;
	for (int i=0; i<n; i++)
	{
		// "first" and "second" are used to access
		// 1st and 2nd element of pair respectively
		cout << vect[i].first << " "
			<< vect[i].second << endl;
	}
	return 0;
}
```

**EDIT**: using c++14, the best solution is very easy to write thanks to lambdas that can now have parameters of type `auto`. **This is my current favorite solution**

```cpp
std::sort(v.begin(), v.end(), [](auto &left, auto &right) {
    return left.second < right.second;
});
```

---

**ORIGINAL ANSWER**:

Just use a custom comparator (it's an optional 3rd argument to `std::sort`)

```cpp
struct sort_pred {
    bool operator()(const std::pair<int,int> &left, const std::pair<int,int> &right) {
        return left.second < right.second;
    }
};

std::sort(v.begin(), v.end(), sort_pred());
```

If you're using a C++11 compiler, you can write the same using lambdas:

```cpp
std::sort(v.begin(), v.end(), [](const std::pair<int,int> &left, const std::pair<int,int> &right) {
    return left.second < right.second;
});
```

**EDIT**: in response to your edits to your question, here's some thoughts ... if you **really** wanna be creative and be able to reuse this concept a lot, just make a template:

```cpp
template <class T1, class T2, class Pred = std::less<T2> >
struct sort_pair_second {
    bool operator()(const std::pair<T1,T2>&left, const std::pair<T1,T2>&right) {
        Pred p;
        return p(left.second, right.second);
    }
};
```

then you can do this too:

```cpp
std::sort(v.begin(), v.end(), sort_pair_second<int, int>());
```

or even

```cpp
std::sort(v.begin(), v.end(), sort_pair_second<int, int, std::greater<int> >());
```
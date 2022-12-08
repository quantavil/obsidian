[[Utility]] 
**Pair** in C++ behaves similarly to tuple in python. It consists of two elements **{first, second}**. The first element is referred to as first while the second element is referred to as second. This order must be fixed (first, second). The header file for Pair in C++ is `<utility>`, and it is also a container class in STL (standard template library).

**SYNTAX :**
```cpp
pair <data_type1, data_type2> pair_name;
```

**INITIALIZATION :**

```cpp
pair  g1;         //default
pair  g2(1, 'a');  //initialized,  different data type
pair  g3(1, 10);   //initialized,  same data type
pair  g4(g3);    //copy of g3
g2 = make_pair(1, 'a'); // using the make_pair() function.
g2 = {1, 'a'};
pair < pair < int, int > , int > p1; // Nested Pir
```

## C++ Pair STL Member Functions

### make_pair
This template function allows to create a value pair without writing the types explicitly.   

**SYNTAX :**
```cpp
Pair_name = make_pair (value1,value2);
```

**EXAMPLE :**
```cpp
p1 = make_pair("Apple", 4.56);
cout << p1.first << " " << p1.second ; // Apple 4.56
```

### swap
This function swaps the contents of one pair object with the contents of another pair object. The pairs must be of the same type.

**SYNTAX :**
```cpp
pair1.swap(pair2) ;
```

**EXAMPLE :**
```cpp
pair<char, int> pair1 = make_pair('A', 1); //A1
pair<char, int> pair2 = make_pair('B', 2); //B2
pair1.swap(pair2); //swaping 
//  pair1 --> B2
//  pair2 --> A1
```

### tie
It creates a tuple of lvalue references to its arguments i.e., to unpack the tuple (or here pair) values into separate variables.
“ignore” keyword ignores a particular tuple element from getting unpacked.   

However, tuples can have multiple arguments but pairs only have two arguments. So, in the case of pair of pairs, unpacking needs to be explicitly handled.

**SYNTAX :**
```cpp
tie(a, b) = pair1;
```

**EXAMPLE  :**

```cpp
pair<int, int> pair1 = { 1, 2 };
int a, b;
tie(a, b) = pair1;
cout << a << " " << b ; // 1 2

pair<int, int> pair2 = { 3, 4 };
tie(a, ignore) = pair1; 
cout << a << " " << b ; // 3 2

// (b remains same)
 
/********************************************************/
pair<int, pair<int, char> > pair3 = { 3, { 4, 'a' } };
int x, y;
char z;

x = pair3.first; 
cout << x; // 3

tie(y, z) = pair3.second  
cout << y << " " << z ; // 4 'a'

// tie(x,y,z) = pair3; Gives compilation error
// tie(x, tie(y,z)) = pair3; Gives compilation error
// Each pair needs to be explicitly handled
```

## Nested Pairs

We can use nested pairs, also. The syntax to declare nested pairs in C++ is as follows :

```cpp
pair <pair <dt1, dt2>, dt3> p1;
```

**EXAMPLE :**

```cpp
pair < pair < int, int > , int > p1;
p1 = make_pair(make_pair(1, 2), 3);
cout << p1.first.first << " " << p1.first.second << " " << p1.second << endl; // 1 2 3
```
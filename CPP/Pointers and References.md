# Pointers and References

## What is a Pointer ?
- A variable
	- whose value is an address
- What can be at that address ?
	- Another Variable
	- A function
- Pointers points to variable or functions ?
- To use the data that the pointer pointing  to  you must know  its type .

---
## Why use Pointer ?
![[img34.png]]

![[img35.png]]

![[img37.png]]


---
## Accessing Pointer Address

```cpp
[[include]] <iostream>

using std::cout;
using std::endl;



int main() {
    int num {10};
    cout << "num = " << num << endl;
    cout << "The size of the num is " << sizeof(num) << endl;
    cout << "Address of the num is " << &num << endl;
    cout << "===========================================" << endl;
    int *p ; // we didn't initialize the pointer
    cout << "Value of p is " << p << endl; // garbage value
    cout << "Address of p is " << &p << endl; // address of the pointer
    cout << "The size of p is " << sizeof(p) << endl;
    cout << "===========================================" << endl;
    p = nullptr; // we initialize the pointer to nullptr
    cout << "Value of p is " << p << endl; // garbage value
	cout << "Address of p is " << &p << endl; // address of the pointer
    cout << "===========================================" << endl;

    // Don't confuse size of a pointer with size of a variable
    // All pointers are 4 bytes in size, irrespective of the size of the variable they point to

    int *p1 = nullptr; double *p2 = nullptr; unsigned long long *p3 = nullptr;
    cout << "The size of p1 is " << sizeof(p1) << endl;
    cout << "The size of p2 is " << sizeof(p2) << endl;
    cout << "The size of p3 is " << sizeof(p3) << endl;
}
```

>num = 10
>The size of the num is 4
>Address of the num is 0x61ff00
>===========================================
>Value of p is 0x61ff08
>Address of p is 0x61fefc
>The size of p is 4
>===========================================
>Value of p is 0
>Address of p is 0x61fef8
>===========================================
>The size of p1 is 4
>The size of p2 is 4
>The size of p3 is 4


![[img38.png]]

---

## Dereferencing the Pointer

Accessing the data we are pointing to - Dereferencing the Pointer

```cpp
[[include]] <iostream>
[[include]] <string>
[[include]] <vector>
using std::cout;
using std::endl;
using std::string;
using std::vector;


int main() {
    int score {100};
    int *score_ptr {&score};
    // ! If Score Pointer has a valid Address 
    
    // ! Then you can access the data at the address contained in the score_ptr using the dereferening operator *
    cout << *score_ptr << endl;
    cout << score_ptr<<endl; // address of the score stored in score_ptr  pointer

    *score_ptr = 200;
    cout << *score_ptr << endl;
    cout << score << endl;

    cout << "=================================="<< endl;
    double high_temp {40.7};
    double low_temp {10.4};

    double *temp_ptr {&high_temp};

    cout << *temp_ptr << endl; 

    temp_ptr = &low_temp;
    cout << *temp_ptr << endl;
    
    cout << "=================================" << endl;

    string name {"Frank"};
    string *string_ptr {&name};

    cout << *string_ptr<<endl;
    name = "James";
    cout << *string_ptr<<endl;

	cout << "===================================="<<endl;

    vector <string> stooges {"Harry","Billy", "Magareta"};
    vector <string> *vector_ptr {nullptr};

    vector_ptr = &stooges;
    
    cout << "First Stooge : " << (*vector_ptr).at(0) << endl; // () necessary
    cout << "Stooges : ";
    for (auto stooges : *vector_ptr ) {
        cout << stooges << " ";
    }
    cout << endl;
    return 0;
}
```

>100
>0x61fefc
>200
>200
>==================================
>40.7
>10.4
>=================================
>Frank
>James
>====================================
>First Stooge : Harry
>Stooges : Harry Billy Magareta

---

## Dynamic Memory Allocation

C++ supports three basic types of memory allocation, of which you’ve already seen two.

-   **Static memory allocation** happens for static and global variables. Memory for these types of variables is allocated once when your program is run and persists throughout the life of your program.
-   **Automatic memory allocation** happens for function parameters and local variables. Memory for these types of variables is allocated when the relevant block is entered, and freed when the block is exited, as many times as necessary.
-   **Dynamic memory allocation** is the topic of this article.

Both static and automatic allocation have two things in common:

-   The size of the variable / array must be known at compile time.
-   Memory allocation and deallocation happens automatically (when the variable is instantiated / destroyed).

Most of the time, this is just fine. However, you will come across situations where one or both of these constraints cause problems, usually when dealing with external (user or file) input.

For example, we may want to use a string to hold someone’s name, but we do not know how long their name is until they enter it. Or we may want to read in a number of records from disk, but we don’t know in advance how many records there are. Or we may be creating a game, with a variable number of monsters (that changes over time as some monsters die and new ones are spawned) trying to kill the player.

If we have to declare the size of everything at compile time, the best we can do is try to make a guess the maximum size of variables we’ll need and hope that’s enough:

```cpp
char name[25]; // let's hope their name is less than 25 chars!
Record record[500]; // let's hope there are less than 500 records!
Monster monster[40]; // 40 monsters maximum
Polygon rendering[30000]; // this 3d rendering better not have more than 30,000 polygons!
```

This is a poor solution for at least four reasons:

1. It leads to wasted memory if the variables aren’t actually used.
2. how do we tell which bits of memory are actually used? For strings, it’s easy: a string that starts with a \\0 is clearly not being used. 
3. most normal variables (including fixed arrays) are allocated in a portion of memory called the **stack**. The amount of stack memory for a program is generally quite small -- Visual Studio defaults the stack size to 1MB. If you exceed this number, stack overflow will result, and the operating system will probably close down the program.

Fortunately, these problems are easily addressed via dynamic memory allocation. **Dynamic memory allocation** is a way for running programs to request memory from the operating system when needed. This memory does not come from the program’s limited stack memory -- instead, it is allocated from a much larger pool of memory managed by the operating system called the **heap**. On modern machines, the heap can be gigabytes in size.

**Dynamically allocating single variables**

To allocate a _single_ variable dynamically, we use the scalar (non-array) form of the **new** operator:

```cpp
new int; // dynamically allocate an integer (and discard the result)
```

In the above case, we’re requesting an integer’s worth of memory from the operating system. The new operator creates the object using that memory, and then returns a pointer containing the _address_ of the memory that has been allocated.

Most often, we’ll assign the return value to our own pointer variable so we can access the allocated memory later.

```cpp
int* ptr{ new int }; // dynamically allocate an integer and assign the address to ptr so we can access it later
```

We can then perform indirection through the pointer to access the memory:

```cpp
*ptr = 7; // assign value of 7 to allocated memory
```

If it wasn’t before, it should now be clear at least one case in which pointers are useful. Without a pointer to hold the address of the memory that was just allocated, we’d have no way to access the memory that was just allocated for us!

**How does dynamic memory allocation work?**

This memory used by your application is divided into different areas, each of which serves a different purpose. One area contains your code. Another area is used for normal operations (keeping track of which functions were called, creating and destroying global and local variables, etc…). However, much of the memory available just sits there, waiting to be handed out to programs that request it.

When you dynamically allocate memory, you’re asking the operating system to reserve some of that memory for your program’s use. If it can fulfill this request, it will return the address of that memory to your application. From that point forward, your application can use this memory as it wishes. When your application is done with the memory, it can return the memory back to the operating system to be given to another program.

Unlike static or automatic memory, the program itself is responsible for requesting and disposing of dynamically allocated memory.

**What does it mean to delete memory?**

The delete operator does not _actually_ delete anything. It simply returns the memory being pointed to back to the operating system. The operating system is then free to reassign that memory to another application (or to this application again later).


**Dangling pointers**

<mark style="background: [[FFB86CA6]];">A pointer that is pointing to deallocated memory is called a dangling pointer.  </mark> Indirection through- or deleting a dangling pointer will lead to undefined behavior. Consider the following program:
```cpp
[[include]] <iostream>

int main()
{
    int* ptr{ new int }; // dynamically allocate an integer
    *ptr = 7; // put a value in that memory location

    delete ptr; // return the memory to the operating system.  ptr is now a dangling pointer.

    std::cout << *ptr; // Indirection through a dangling pointer will cause undefined behavior
    delete ptr; // trying to deallocate the memory again will also lead to undefined behavior.

    return 0;
}
```

Best practice

Set deleted pointers to nullptr unless they are going out of scope immediately afterward.

**Operator new can fail**

When requesting memory from the operating system, in rare circumstances, the operating system may not have any memory to grant the request with.

By default, if new fails, a _bad\_alloc_ exception is thrown. 

```cpp
int* value { new (std::nothrow) int }; // value will be set to a null pointer if the integer allocation fails
```

In the above example, if new fails to allocate memory, it will return a null pointer instead of the address of the allocated memory.


**Memory leaks**

Memory leakage occurs in C++ when programmers allocates memory by using new keyword and forgets to deallocate the memory by using delete() function or delete\[\] operator. One of the most memory leakage occurs in C++ by using wrong delete operator.   
The delete operator should be used to free a single allocated memory space, whereas the delete [] operator should be used to free an array of data values.   
**Disadvantage with memory leakage:**   
If a program has memory leaks, then its memory usage is satirically increasing since all systems have limited amount of memory and memory is costly. Hence it will create problems.

**How to avoid Memory Leak?**

-   Instead of managing memory manually, try to use smart pointers where applicable.
-   use *std::string* instead of char \* . *The std::string class handles all memory management internally, and it’s fast and well-optimized.*
-   Never use a raw pointer unless it’s to interface with an older lib.
-   The best way to avoid memory leaks in C++ is to have as few new/delete calls at the program level as possible – ideally NONE.

**Conclusion**

Operators new and delete allow us to dynamically allocate single variables for our programs.

Dynamically allocated memory has dynamic duration and will stay allocated until you deallocate it or the program terminates.

Be careful not to perform indirection through dangling or null pointers

```cpp
[[include]] <iostream>

using namespace std;
int main() {
    // dynamic memory allocation
    int *ptr {nullptr};
    ptr = new int; // allocate memory for an int
    cout << "ptr: " << ptr << endl;
    cout << "*ptr: " << *ptr << endl; // garbage value
    *ptr = 10; // assign 10 to the allocated memory
    cout << "*ptr: " << *ptr << endl;  // dereference ptr to get the value
    delete ptr; // deallocate memory
    cout << "*ptr: " << *ptr << endl; // garbage value

    cout << "------------------------------------" << endl;

    size_t size {0};
    double *temp_ptr {nullptr}; 
    cout << "Enter the size of the array: ";
    cin >> size;
    temp_ptr = new double[size]; // allocate memory for an array of doubles
    cout << "temp_ptr: " << temp_ptr << endl;
    // temp_ptr = nullptr; // before deallocation : Memory leak
    delete [] temp_ptr; // deallocate memory
}
```

>ptr: 0xfd16e0
>*ptr: 16609152
>\*ptr: 10
>\*ptr: 16609152
>\------------------------------------
>Enter the size of the array: 10
>temp_ptr: 0xfd6f80

---
## Relationship between Arrays and Pointers
- The Value of the array name is the address of the first element of array.
- The value of the pointer variable is an address.
- If the pointer points to the same datatype as the array element then the  pointers name and array name can be used interchangeably (almost).

![[img39.png]]

```cpp
[[include]] <iostream>

using namespace std;

int main() {
    int score[] {100,95,89};
    cout<< "Value of score is " << score << endl;

    int *score_ptr {score}; // no need of & as score is already a pointer
    cout<< "Value of score_ptr is " << score_ptr << endl;

    cout << "\nArray subscipt notation ------------" << endl;
    cout << score[0] << endl; // &score at + 0 
    cout << score[1] << endl; // &score at + 1 
    cout << score[2] << endl; // &score at + 2 

    cout << "\nPointer subscipt notation ------------" << endl;
    cout << score_ptr[0] << endl; // &score at + 0
    cout << score_ptr[1] << endl; // &score at + 1
    cout << score_ptr[2] << endl; // &score at + 2

    cout << "\nPointer offset notation ------------" << endl;
    cout << "The Address in score_ptr: "<< score_ptr << " and the value is : "<< *score_ptr << endl; // &score at + 0
    cout << "The Address in score_ptr: "<< score_ptr + 1 << " and the value is : "<< *(score_ptr + 1) << endl; // &score at + 1
    cout << "The Address in score_ptr: "<< score_ptr + 2 << " and the value is : "<< *(score_ptr + 2) << endl; // &score at + 2

    cout << "\nArray offset notation ------------" << endl;
    cout << "The Address in score: "<< score << " and the value is : "<< *score << endl; // &score at + 0
    cout << "The Address in score: "<< score + 1 << " and the value is : "<< *(score + 1) << endl; // &score at + 1
    cout << "The Address in score: "<< score + 2 << " and the value is : "<< *(score + 2) << endl; // &score at + 2

}
```

>Value of score is 0x61fef0
>Value of score_ptr is 0x61fef0
>
>Array subscipt notation ------------
>100
>95
>89
>
>Pointer subscipt notation ------------
>100
>95
>89
>
>Pointer offset notation ------------
>The Address in score_ptr: 0x61fef0 and the value is : 100
>The Address in score_ptr: 0x61fef4 and the value is : 95
>The Address in score_ptr: 0x61fef8 and the value is : 89
>
>Array offset notation ------------
>The Address in score: 0x61fef0 and the value is : 100
>The Address in score: 0x61fef4 and the value is : 95
>The Address in score: 0x61fef8 and the value is : 89

---

## Pointer Arithmetic

- pointers can be used in 
	- assignment expression 
	- mathematical expression 
	- comparison expression
- C++ allow pointer arithmetic
- point arithmetic only makes sense with raw arrays
- (++) increment a pointer to point to the next array element `int_ptr++`
- (--) decrement a pointer to point to the previous array element `int_ptr--`
-  (+) increment pointer by n \* size of (type) `int_ptr += n`
-  (-) decrement pointer by n \* size of (type) `int_ptr -= n`
- Pointer Arithmetic  is machine specific as the size of C++ types varies from machine to machine
- **Subtracting two pointer** :  If b if both pointer points to same data type then the result will number of elements between two pointers. `int_n = int_ptr2 - int_ptr1` else  Error
- ![[img40.png]]
- ![[img41.png]]

```cpp
[[include]] <iostream>

using namespace std;

int main() {
    int score[] {100,95,89,68,-1};
    int *score_ptr = score;

    while (*score_ptr != -1) {
        cout << *score_ptr << endl;
        score_ptr++;
    }

    cout << "\n------------------------" << endl;
    score_ptr = score;
    while (*score_ptr != -1) {
        cout << *score_ptr++ << endl; // (*score_ptr)++  dereferance first then increment
    }

    cout << "\n------------------------" << endl;
    char name[] {"John"};
    char *char_ptr1 {nullptr};
    char *char_ptr2 {nullptr};

    char_ptr1 = &name[0]; // J
    char_ptr2 = &name[3]; // n

    cout << char_ptr2 - char_ptr1 << endl; // 3

}
```

>100
>95
>89
>68
>
>\------------------------
>100
>95
>89
>68
>
>\------------------------
>3

---

## Const and Pointers

There are several ways to qualify pointers using const
- Pointers to constants
- Constant pointers
- Constant pointers to constants

![[img42.png]]
![[img43.png]]
![[img44.png]]

---

## Passing Pointer to a function
**Pass By Reference with pointers  - Calling the function**

```cpp
[[include]] <iostream>
using namespace std;

void double_data (int *int_ptr)
{
    *int_ptr *= 2; // dereferencing the pointer first 
}
int main() {
    int value = 10;
    int *int_ptr {&value}; // pointer to value

    double_data(int_ptr); // passing the pointer to the function
    cout << "value = " << value << endl;

    double_data(&value); // passing address of value
    cout << "value = " << value << endl;


    return 0;
}

```

>value = 20
>value = 40

```cpp
[[include]] <iostream>
using namespace std;

void swap(int *a, int *b) {
    int temp = *a;
    *a = *b;
    *b = temp;
}

int main() {
    int x{1}, y{2};
    cout << "Before swap: x = " << x << ", y = " << y << endl;
    swap(&x, &y);
    cout << "After swap: x = " << x << ", y = " << y << endl;

    return 0;
}
```
>Before swap: x = 1, y = 2
>After swap: x = 2, y = 1

---

## Returning Pointer from a function

```cpp
[[include]] <iostream>

using namespace std;

int *largest_int (int *a , int *b) {
    if (*a > *b) {
        return a; // return a pointer
    } else {
        return b; // return b pointer
    }
}

int main () {
    int a = 5;
    int b = 10;
    int *p = largest_int (&a, &b);
    cout << "The largest int is " << *p << endl;
    return 0;
}
```

> The largest int is 10

```cpp
[[include]] <iostream>

using namespace std;

int *create_array(size_t size, int value =0)
{
    int *arr {nullptr};
    arr = new int[size];
    for (size_t i {0}; i < size; i++) {
        *(arr + i) = value; // using pointer offset notation, you can also use arr[i] = value;
    }
    return arr;
}

int main () {
    int *arr {nullptr};
    arr = create_array(10, 10);
    for (size_t i {0}; i < 10; i++) {
        cout << arr[i] << " ";
    }
    delete [] arr;
    return 0;
}
```

> 10 10 10 10 10 10 10 10 10 10 

---

## Potential Pointer Pitfalls

- Uninitialized Pointer :  `int *int_ptr // pointing anywhere`
- Dangling Pointer : A pointer pointing to a memory location that has been deleted (or freed) is called dangling pointer.  OR Pointer that points to the memory that is invalid
	- for eg two pointer are pointing to the same data 1 pointer releases the data with delete , the other pointer access the release data
```cpp
int *p = new int; // request memory
*p = 5; // store value

delete p; // free up the memory
// now p is a dangling pointer
```
- not checking if `new` failed : If `new` fails an exception is thrown , we can use exceptional handling to catch exceptions. Dereferencing a null pointer will cause your program to crash.
- Memory Leak

---

## References
- An alias for variable
- Must be initialized to a variable when declared
- Cannot be null
- Once initialized cannot be made to refer to different variable
- Very useful as function parameters
- Might be helpful to think of a reference as a constant pointer that is automatically dereferenced.

```cpp
[[include]] <iostream>
[[include]] <vector>

using namespace std;

int main() {
    int num {100};
    int &ref {num};
    cout << "num: " << num << endl;
    cout << "ref: " << ref << endl;
    cout << "----------------------------------------" << endl;

    num = 200;
    cout << "num: " << num << endl;
    cout << "ref: " << ref << endl;
    cout << "----------------------------------------" << endl;

    ref = 300;
    cout << "num: " << num << endl;
    cout << "ref: " << ref << endl;
    cout << "----------------------------------------" << endl;

    vector<string> stooges = { "Larry", "Moe", "Curly" };
    for (auto str: stooges)
        str = "Funny "; // changes the copy of the string str

    for (auto str: stooges)
        cout << str << " ";
    cout << endl;

    for (auto &str: stooges)
        str = "Funny"; // changes the actual string stooges[i]

    for (auto str: stooges)
        cout << str << " ";
    /*for (auto const &str: stooges)
        str = "Funny "; // compile error*/
}
```

>num: 100
>ref: 100
>\----------------------------------------
>num: 200
>ref: 200
>\----------------------------------------
>num: 300
>ref: 300
>\----------------------------------------
>Larry Moe Curly
>Funny Funny Funny

---

## L values and R values

![[img45.png]]
![[img46]]
![[img46.png]]

![[img47.png]]

![[img48.png]]

![[img49.png]]

![[img50.png]]

---

 ## When to use Pointer vs. references parameters

- **Pass-By-Value : **
	1.  When the function doesn't modify the actual parameter, and 
	2.  the parameter is small and efficient to copy like simple types (int, char, double, etc.)
- **Pass-by-reference using a pointer**
	1. when the function does modify the actual parameter, and
	2. the parameter is expensive to copy, and
	3. Its *OK* to the pointer is allowed a *nullptr* value
- **Pass-by-reference using a reference**
	1. when the function does modify the actual parameter, and
	2. the parameter is expensive to copy, and
	3. The parameter will *never be nullptr* 

---

## Section Challenge
Print out Cartesian Product of two arrays.

```cpp
[[include]] <iostream>

using namespace std;

void print(const int *const arr, size_t size) { 
    cout << "[";
    for (size_t i {0};i < size; ++i) {
        cout << arr[i] << ", ";
    }
    cout << "]" << endl;
}

// Cartesian product of two arrays
int *cartPro(const int *const arr1 , size_t size1, const int *const arr2 , size_t size2) {
    int *result = new int[size1 * size2];

    int pos {0};
    for (size_t i {0}; i < size1; ++i) {
        for (size_t j {0}; j < size2; ++j) {
            result[pos] = arr1[i] * arr2[j];
            ++pos;
        }
    }
    return result;
}
int main() {
    const size_t size1 {5};
    const size_t size2 {3};

    int arr1[size1] {1, 2, 3, 4, 5};
    int arr2[size2] {7, 8, 9};

    cout << "arr1: ";
    print(arr1, size1);
    cout << "arr2: ";
    print(arr2, size2);
    cout << "cartPro: ";
    int *result = cartPro(arr1, size1, arr2, size2);
    print(result, size1 * size2);
    delete[] result;
    return 0;
}
```

>arr1: [1, 2, 3, 4, 5, ]
>arr2: [7, 8, 9, ]
>cartPro: [7, 8, 9, 14, 16, 18, 21, 24, 27, 28, 32, 36, 35, 40, 45, ]
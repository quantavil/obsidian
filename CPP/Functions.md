
	
You already know that every executable program must have a function named _main_ (which is where the program starts execution when it is run). However, as programs start to get longer and longer, putting all the code inside the _main_ function becomes increasingly hard to manage. Functions provide a way for us to split our programs into small, modular chunks that are easier to organize, test, and use. Most programs use many functions. The C++ standard library comes with plenty of already-written functions for you to use -- however, it’s just as common to write your own. Functions that you write yourself are called user-defined functions.

A function call is an expression that tells the CPU to interrupt the current function and execute another function. The CPU “puts a bookmark” at the current point of execution, and then calls (executes) the function named in the function call. When the called function ends, the CPU returns back to the point it bookmarked, and resumes execution.

- Functions make our program more modular , more readable , easy to maintain and debug and easy to reuse.

![[img15.png]]

An example of a user-defined function

First, let’s start with the most basic syntax to define a user-defined function. For the next few lessons, all user-defined functions will take the following form:

```
return-type identifier() // identifier replaced with the name of your function
{
// Your code here
}

```

Let’s quickly go over the 4 main elements of this:

-   In this lesson, we’ll use a _return-type_ of _int_ (for function _main()_) or _void_ (otherwise). We’ll talk more about return types and return values in the next lesson ([2.2 -- Function return values](https://www.learncpp.com/cpp-tutorial/function-return-values/)). For now, you can ignore these.
-   Just like variables have names, so do user-defined functions. The _identifier_ is the name of your user-defined function.
-   The parentheses after the identifier tell the compiler that we’re defining a function.
-   The curly braces and statements in between are called the function body. This is where the statements that are part of your function will go.

---

Using Predefined Functions

```cpp
[[include]] <iostream>
[[include]] <cmath>
[[include]] <time.h>
using namespace std;

int main() {
    int random {};
    size_t count {10}; //number of random numbers to generate
    int min {1}; //minimum value of random number , lower bound inclusive
    int max {6}; //maximum value of random number, upper bound inclusive

    cout << "RAND_MAX = " << RAND_MAX << endl;

    // nullptr is basically a pointer to a null pointer and is better than NULL because it  the literal 0 has a bad tendency to acquire the type int
    srand(time(nullptr)); //seed random number generator  with current time

    for (size_t i {1}; i <= count ;++i) {
        random = rand() % (max - min + 1) + min;
        cout << random << endl;
    }

    return 0;

}
```

>RAND_MAX = 32767
>5 6 5 1 2 3 2 5 4 5

---

Here is a sample program that shows how a new function is defined and called:

```cpp
[[include]] <iostream> // for std::cout

// Definition of user-defined function doPrint()
void doPrint() // doPrint() is the called function in this example
{
    std::cout << "In doPrint()\n";
}

// Definition of function main()
int main()
{
    std::cout << "Starting main()\n";
    doPrint(); // Interrupt main() by making a function call to doPrint().  main() is the caller.
    std::cout << "Ending main()\n"; // this statement is executed after doPrint() ends

    return 0;
}
```

>Starting main()
>In doPrint()
>Ending main()

---

Calling functions more than once

One useful thing about functions is that they can be called more than once. Here’s a program that demonstrates this:

```cpp
[[include]] <iostream> // for std::cout

void doPrint()
{
    std::cout << "In doPrint()\n";
}

// Definition of function main()
int main()
{
    std::cout << "Starting main()\n";
    doPrint(); // doPrint() called for the first time
    doPrint(); // doPrint() called for the second time
    std::cout << "Ending main()\n";

    return 0;
}
```


> Starting main()
> In doPrint()
> In doPrint()
> Ending main()

Since _doPrint_ gets called twice by _main_, _doPrint_ executes twice, and _In doPrint()_ gets printed twice (once for each call).

 ## Functions calling functions calling functions

You’ve already seen that function _main_ can call another function (such as function _doPrint_ in the example above). Any function can call any other function. In the following program, function _main_ calls function _doA_, which calls function _doB_:

```cpp
[[include]] <iostream> // for std::cout

void doB()
{
    std::cout << "In doB()\n";
}


void doA()
{
    std::cout << "Starting doA()\n";

    doB();

    std::cout << "Ending doA()\n";
}

// Definition of function main()
int main()
{
    std::cout << "Starting main()\n";

    doA();

    std::cout << "Ending main()\n";

    return 0;
}
```

>Starting main()
>Starting doA()
>In doB()
>Ending doA()
>Ending main()

## Nested functions are not supported

Unlike some other programming languages(like Python), in C++, functions cannot be defined inside other functions. The following program is not legal:

```cpp
[[include]] <iostream>

int main()
{
    void foo() // Illegal: this function is nested inside function main()
    {
        std::cout << "foo!\n";
    }

    foo(); // function call to foo()
    return 0;
}
```

---

```cpp
[[include]] <iostream>
[[include]] <cmath>
using namespace std;
const double pi = 3.14159265;
void print() {
    cout << "Enter the radius of the circle: ";
}
double area_of_circle(int r)
{
    return pi*r*r;
}
double volume_of_cylinder(int r,int h)
{
    return area_of_circle(r)*h;
}
int main() {
    int r,h;
    print();
    
    cin>>r>>h;
    cout<<volume_of_cylinder(r,h);
    return 0;
}
```
>Enter the radius of the circle: 5
>4
>314.159

---

## Function Prototype

![[img16.png]]

Example of Function Prototype:
```cpp
void function_name(int a, std::string b);
// or
void function_name(int, std::string);


void function_name(int a, std::string b) {
	statements(s);
	return ; // optional
}
```

```cpp
[[include]] <iostream>
[[include]] <cmath>
using namespace std;
const double pi = 3.14159265;

//The order in which you put prototypes doesn't matter
double volume_of_cylinder(int ,int);
void print();
double area_of_circle(int r);


int main() {
    int r,h;
    print();

    cin>>r>>h;
    cout<<volume_of_cylinder(r,h);
    return 0;
}



double volume_of_cylinder(int r,int h)
{
    return area_of_circle(r)*h;
}
void print() {
    cout << "Enter the radius of the circle: ";
}
double area_of_circle(int r)
{
    return pi*r*r;
}
```
>Enter the radius of the circle: 4
>5
>251.327

---

## Function Parameters
- When we call a function we pass in data to that function 
- In the function call they are called arguments
- In the function definition they are called parameters
- They must match in number , order and in type.

![[img17.png]]

```cpp
void say_hello(std::string name) { // fuction expect c++ string object
	cout << "Hello " <<name << endl;
}

say_hello("Frank"); // The compiler will convert c style string literal to   c++ string object

std::string my_dog {"Buster"};
say_hello(my_dog);
```

![[img18.png]]
![[img19.png]]

---
## Function Return Statement
![[img20.png]]


---

```cpp
[[include]] <iostream>
[[include]] <string>
[[include]] <vector>
using namespace std;

void passByValue1(int x);
void passByValue2(string s);


void passByValue1(int x) {
    x = 1000;
}

void passByValue2(string s) {
    s = "Changed";
    cout << s << endl;
}

int main() {
    int x {10};
    int y {20};

    cout << "x before calling passByValue1: " << x << endl;
    passByValue1(x); // x is passed by value which is 10 then x is changed to 1000
    cout << "x after calling passByValue1: " << x << endl;

    cout << "y before calling passByValue1: " << y << endl;
    passByValue1(y); // y is passed by value which is 20 then y is changed to 1000
    cout << "y after calling passByValue1: " << y << endl;

    string name {"John"};
    cout << "name before calling passByValue2: " << name << endl;
    passByValue2(name); // name is passed by value which is John then name is changed to Changed
    cout << "name after calling passByValue2: " << name << endl;

}

```
>x before calling passByValue1: 10
>x after calling passByValue1: 10
>y before calling passByValue1: 20
>y after calling passByValue1: 20
>name before calling passByValue2: John
>Changed
> name after calling passByValue2: John

---
## Default Arguments Value

![[img21.png]]

![[img22.png]]

---

## Function Overloading

Function overloading allows us to create multiple functions with the same name, so long as each identically named function has different parameters (or the functions can be otherwise differentiated). Each function sharing a name (in the same scope) is called an overloaded function (sometimes called an overload for short).

To overload our `add()` function, we can simply declare another `add()` function that takes double parameters:

```cpp
double add(double x, double y)
{
    return x + y;
}
```

```cpp
int add(int x, int y) // integer version
{
    return x + y;
}

double add(double x, double y) // floating point version
{
    return x + y;
}

int main()
{
    return 0;
}
```

The above program will compile. Although you might expect these functions to result in a naming conflict, that is not the case here. Because the parameter types of these functions differ, the compiler is able to differentiate these functions, and will treat them as separate functions that just happen to share a name.

*Functions can be overloaded so long as each overloaded function can be differentiated by the compiler. If an overloaded function can not be differentiated, a compile error will result.*


```cpp
[[include]] <iostream>
[[include]] <string>
[[include]] <vector>
using namespace std;

// This is called Abstraction of a function as it hides the implementation
// Function prototype
void print(int);  
void print(double);
// void print(string);
void print(string, string);
void print(vector<int>);
void print(vector<string>);

void print(int i) {
    cout << "int: " << i << endl;
}

void print(double d) {
    cout << "double: " << d << endl;
}

// void print(string s) {
//     cout << "string: " << s << endl;
// }

void print(vector<int> v) {
    cout << "vector<int>: ";
    for (size_t i : v) {
        cout << i << " ";
    }
}

void print(vector<string> v) {
    cout << "vector<string>: ";
    for (string s : v) {
        cout << s + " ";
    }
    cout << endl;
}

void print(string s1, string end = "\n") {
    cout << s1 << end;
}

int main() {
    print(1);
    print('A'); // char is converted to int
    print(1.034);
    print(1.234F); // float is converted to double
    print("hello"); // c-style string is converted c++ string object
    print(vector<int>{1, 2, 3});

    string s {"C++ is fun!"}; 
    print(s);

    vector<string> v {"Python", "is", "Awesome!"};
    print(v);

    print("C++","OP");
    return 0; 
}


```

>int: 1
>int: 65
>double: 1.034
>double: 1.234
>hello
>`vector<int>`: 1 2 3 C++ is fun!
>`vector<string>`: Python is Awesome!
>`C++OP

---

## Passing Arrays To Functions

![[img24.png]]
![[img25.png]]
![[img26.png]]
![[img27.png]]
![[img28.png]]


 Let say the location of first element   *2*  arr is 0x201023.  So  Whenever C++ compiler sees the array name *my_score*  is evaluated to the above address . In *print_arr*   function the array is passed as a reference as no copy is made that means the address is passed and then it is referring to the main array *my_score* 
 because the array was never copied the address of the array was passed in.

 Therefore the *set_array*  function made difference in main array *my_score*  as the array is not copied.

 It is different from pass  by value as we are not passing any value , but only address  of first element memory location.
 ```cpp
[[include]] <iostream>
[[include]] <string>
using namespace std;

void print_array(const int arr[], size_t n)
{
    for (size_t i{0}; i < n; i++)
        cout << arr[i] << " ";
    cout << endl;
}

void set_array(int arr[], size_t n,int value)
{
    for (size_t i{0}; i < n; i++)
        arr[i] = value;
}

int main() {
    int my_score[10] {2,3,5,7,11,13,17,19,23,29};
    print_array(my_score, 10);
    set_array(my_score, 10,15);
    print_array(my_score, 10);
    return 0;
}

 
```

>2 3 5 7 11 13 17 19 23 29 
>15 15 15 15 15 15 15 15 15 15

---
## Pass By Reference 

`pass by value`, where an argument passed to a function is copied into the function’s parameter:
```cpp
[[include]] <iostream>

void printValue(int y)
{
    std::cout << y << '\n';
} // y is destroyed here

int main()
{
    int x { 2 };

    printValue(x); // x is passed by value (copied) into parameter y (inexpensive)

    return 0;
}
```
One way to avoid making an expensive copy of an argument when calling a function is to use `pass by reference` instead of `pass by value`. When using pass by reference, we declare a function parameter as a reference type (or const reference type) rather than as a normal type. When the function is called, each reference parameter is bound to the appropriate argument. Because the reference acts as an alias for the argument, no copy of the argument is made.
![[img29.png]]


```cpp
[[include]] <iostream>
[[include]] <string>
using namespace std;

// If pass by value, the function will not change the value of the variable
void swap(int &a, int &b)
{
    int temp = a;
    a = b;
    b = temp;
}

int main() {
    int a = 1, b = 2;
    swap(a, b);
    cout << a << " " << b << endl;
    return 0;
}
```
> 2  1

```cpp
[[include]] <iostream>
[[include]] <string>
[[include]] <vector>
using namespace std;

void passByReference1(int &x) {
    x = x + 121;
}
void passByReference2(string& s) {
    s += "Nice !!!";
}
void passByReference3(vector<string> &v1) {
    v1.push_back("Nice !!!");
}
void passByReference4(const vector<int>& v) {
    //v.push_back(10); // error : cannot modify a const object
}

string printVector(const vector<string>& v) {
    string s = "";
    for (auto i : v) {
        s += i;
        s += " ";
    }
    return s;
}

int main() {
    int num = 10;
    cout <<"Before calling passByReference1, num = " << num << endl;
    passByReference1(num);
    cout <<"After calling passByReference1, num = " << num << endl;

    string str = "Super";
    cout <<"Before calling passByReference2, str = " << str << endl;
    passByReference2(str);
    cout <<"After calling passByReference2, str = " << str << endl;

    vector<string> stooges { "Larry", "Moe", "Curly" };
    cout <<"Before calling passByReference3, stooges = " << printVector(stooges) << endl;
    passByReference3(stooges);
    cout <<"After calling passByReference3, stooges = " << printVector(stooges) << endl;
    
    return 0;
}


```
>Before calling passByReference1, num = 10
>After calling passByReference1, num = 131
>Before calling passByReference2, str = Super
>After calling passByReference2, str = SuperNice !!!
>Before calling passByReference3, stooges = Larry Moe Curly
>After calling passByReference3, stooges = Larry Moe Curly Nice !!!

---
## Scope Rule

- C++ uses scope rules to determine where an identifier can be used.
- C++ use  Static or Lexical scoping.
- Local or Block Scope
- Global Scope

#### Local Variables

Variables defined within a function or block are said to be local to those functions.  

-   Anything between ‘{‘ and ‘}’ is said to inside a block.
-   Local variables do not exist outside the block in which they are declared, i.e. they **can not** be accessed or used outside that block.
-   **Declaring local variables**: Local variables are declared inside a block.
- Function Local Variable is only active while Function is executing.
- With nested block inner block can `see` but outer block cannot `see` in.

```cpp
[[include]] <iostream>

int add(int x, int y) // x and y are created and enter scope here
{
    // x and y are visible/usable within this function only
    return x + y;
} // y and x go out of scope and are destroyed here

int main()
{
    int a{ 5 }; // a is created, initialized, and enters scope here
    int b{ 6 }; // b is created, initialized, and enters scope here

    // a and b are usable within this function only
    std::cout << add(a, b) << '\n'; // calls function add() with x=5 and y=6

    return 0;
} // b and a go out of scope and are destroyed here
```


#### Global Variables
-   They are available through out the life time of a program.
-   They are declared at the top of the program outside all of the functions or blocks.
-   **Declaring global variables**: Global variables are usually declared outside of all of the functions and blocks, at the top of the program. They can be accessed from any portion of the program.
-  Global Constants are OK.
- Best practice - don't use global variable.

```cpp
[[include]] <iostream>

// Variables declared outside of a function are global variables
int g_x {}; // global variable g_x

void doSomething()
{
    // global variables can be seen and used everywhere in the file
    g_x = 3;
    std::cout << g_x << '\n';
}

int main()
{
    doSomething();
    std::cout << g_x << '\n';

    // global variables can be seen and used everywhere in the file
    g_x = 5;
    std::cout << g_x << '\n';

    return 0;
}
// g_x goes out of scope her
```

#### Static Local Variable
Using the `static` keyword on a local variable changes its duration from `automatic duration` to `static duration`. This means the variable is now created at the start of the program, and destroyed at the end of the program (just like a global variable). As a result, the static variable will retain its value even after it goes out of scope!

```cpp
[[include]] <iostream>

void incrementAndPrint()
{
    static int s_value{ 1 }; // static duration via static keyword.  This initializer is only executed once.
    ++s_value;
    std::cout << s_value << '\n';
} // s_value is not destroyed here, but becomes inaccessible because it goes out of scope

int main()
{
    incrementAndPrint();
    incrementAndPrint();
    incrementAndPrint();

    return 0;
}
```

```cpp
int generateID()
{   
	// If static is not used the variable will destroyed after each function call there the counter will remain zero
    static int s_itemID{ 0 };
    return s_itemID++; // makes copy of s_itemID, increments the real s_itemID, then returns the value in the copy
}
```


## How do Function Call Work
![[img30.png]]
![[img31.png]]
![[img32.png]]
![[img33.png]]



## Inline Function

If make a function as inline, then the compiler replaces the function calling location with the definition of the inline function at compile time.

**Let's understand the difference between the normal function and the inline function.**

Inside the **main()** method, when the function fun1() is called, the control is transferred to the definition of the called function. The addresses from where the function is called and the definition of the function are different. This control transfer takes a lot of time and increases the overhead.

When the inline function is encountered, then the definition of the function is copied to it. In this case, there is no control transfer which saves a lot of time and also decreases the overhead.

```cpp
[[include]] <iostream>
using namespace std;


//this function is the fastest bacause it executes at compile time and is really fast , 
//but dont use it for like a big function  
inline int cube(int s)
{
    return s*s*s;
}
int main()
{
    cout << "The cube of 3 is: " << cube(3) << "\n";
    return 0;
}
```

>[!Output]
>The cube of 3 is: 27


## Recursive Function
Recursive function calls generally work just like normal function calls. However, the program above illustrates the most important difference with recursive functions: you must include a recursive termination condition, or they will run “forever” (actually, until the call stack runs out of memory). A **recursive termination** is a condition that, when met, will cause the recursive function to stop calling itself.

```cpp
[[include]] <iostream>
using namespace std;

unsigned long long int fibbonaci (unsigned long int n) {
    if (n <=1 ) {
        return n;
    }
    return fibbonaci(n-1) + fibbonaci(n-2);
}

int main() {
    for (size_t count {0}; count < 13; count++){
        cout << fibbonaci(count) << " ";
    }
    return 0;
}
```

> [!Output] 
> 0 1 1 2 3 5 8 13 21 34 55 89 144 
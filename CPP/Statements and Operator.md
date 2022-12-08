# Statements and Operator 

C++ expression consists of operators, constants, and variables which are arranged according to the rules of the language.  

```cpp

32 // literal

x // variable

(a+b) - c 

(x/y) -z 

4a2 - 5b +c 

(a+b) * (x+y) 

```

A statement is:

- A complelete line of code that perform some action

- usually terminate with semi-colon ;

- usually contain many expression

- C++ has many type of statement:

 - expression, null, compound, selection, iteration, declaration, jump, control flow, try block, and others.

```cpp

[[include]] <iostream> 

using namespace std; 

int main() 

{ 

 int a;
 int b;
 int p[] {1,2,3};
 int x; // variable declaration.
 int y;
 int z;

 int *ptr; // pointer declaration

 cin >> y >> z;

 x=(3/2) + 2; // constant expression or assignment

 z=x+y; // integral expression

 ptr=p; // assigning base address of array to the pointer ptr // pointer expression

  

 bool v = x>z; // relational expression

 a>10 || b==5; // Logical expression

 x >> 3; // bitwise expression

  

 a=b=80; // chained assignment

 a=10+(b=90); // embedded assignment expression

 a+=10; // compound assignment

 return 0; 

}

```

  

---

  

Increment & decrement Operator  

```cpp

[[include]] <iostream> 

using namespace std; 

int main() 

{ int counter {10};

 int result {0};

 int anotherResult {0};

 // Example 1 simple increment

 counter = counter + 1;
 cout << counter << endl;
 counter++;
 cout << counter << endl;
 ++counter;
 cout << counter << endl;

  

 cout << "------------------------" << endl;

 // Example 2 pre-increment

 counter = 10;

 result = 0;

 cout << "counter = " << counter << endl;

 // * result = ++counter;

 anotherResult = ++counter + 10;

 cout << "result = " << result << endl;

 cout << "anotherResult = " << anotherResult << endl;

 cout << "counter = " << counter << endl;

  

 cout << "------------------------" << endl;

 // Example 3 post-increment

 counter = 10;

 result = 0;

 cout << "counter = " << counter << endl;

 // * result = counter++;

 anotherResult = counter++ + 10;

 cout << "result = " << result << endl;

 cout << "anotherResult = " << anotherResult << endl;

 cout << "counter = " << counter << endl;

  

 return 0;

}

```

  

>```cpp

>11

>12

>13

>------------------------

>counter = 10

>result = 0

>anotherResult = 21

>counter = 11

>------------------------

>counter = 10

>result = 0

>anotherResult = 20

>counter = 11

>```

  

---


![imag5](img/img5.png)

  
---

  

```cpp

[[include]] <iostream>

  

using namespace std;

  

int main() {

int a,b,c;

int sum {} ;

cout<<"Enter the three integer: ";

cin >> a >> b >> c;

sum = a + b + c;

cout << "Sum of three integer is: " << sum << endl;

cout << "Average of three integer is: " << static_cast<double>(sum)/3 << endl; // static_cast<double>() is used to convert one data type to other data type.

// average = double(sum)/3; // This is also valid. But it is not recommended, used in old C.

return 0;

}

```

  

>Enter the three integer: 3 5 8

>

>Sum of three integer is: 16

>

>Average of three integer is: 5.33333

  

---

  

Assignment Operator

  

```cpp

[[include]] <iostream>

  

using namespace std;

  

int main() {

 int num;

 const int lower {10};

 const int upper {20};

 cout << boolalpha;

 cout << "Enter a number between " << lower << " and " << upper << ": ";

 cin >> num;

 cout << num << " is between " << lower << " and " << upper << ": "<< (num >= lower && num <= upper) << endl;

  

 cout << "Enter a numbe rwhich is outside " << lower << " and " << upper << " bounds : ";

 cin >> num;

 cout << num << " is outside " << lower << " and " << upper << " bounds: " << (num < lower || num > upper) << endl;

 return 0;

}

```

  

>Enter a number between 10 and 20: 45

>

>45 is between 10 and 20: false

>

>Enter a numbe rwhich is outside 10 and 20 bounds : 56

>

>56 is outside 10 and 20 bounds: true

  

---

  

Compound Assignment Operator

  

![img6](img/img6.png)

  

---

  

Operator Precedence

  

![img7](img/img7.png)

  

---

  

```cpp

[[include]] <iostream>

  

using namespace std;

  

int main() {

 // define conversion values in cents

 const int dollarValue {100};

 const int quarterValue {25};

 const int dimeValue {10};

 const int nickelValue {5};

 const int pennyValue {1};

 int totalCents {0};

 /******* Method 1 *******/

 int balance {},dollars {},quarters {},dimes {},nickels {},pennies {};

 cout << "Enter the amount in balance: ";

 cin >> totalCents;

  

 dollars = totalCents / dollarValue;

 balance = totalCents - (dollars * dollarValue);

  

 quarters = balance / quarterValue;

 balance = balance - (quarters * quarterValue);

  

 dimes = balance / dimeValue;

 balance = balance - (dimes * dimeValue);

  

 nickels = balance / nickelValue;

 balance = balance - (nickels * nickelValue);

  

 pennies = balance / pennyValue;

 balance = balance - (pennies * pennyValue);

  

 cout << "I have the change for you: ";

 cout << "You have " << dollars << " dollars, " << quarters << " quarters, " << dimes << " dimes, " << nickels << " nickels, and " << pennies << " pennies." << endl;

  

 /******* Method 2 *******/

  

 cout << "You can provide change as follows: " << "\n dollar : " << totalCents/dollarValue << " \n quarter : " << totalCents%dollarValue/quarterValue << " \n dime : " << totalCents%dollarValue%quarterValue/dimeValue << " \n nickel : " << totalCents%dollarValue%quarterValue%dimeValue/nickelValue << " \n penny : " << totalCents%dollarValue%quarterValue%dimeValue%nickelValue << endl;

  

 return 0;

}

```

  

>Enter the amount in balance: 1209

>

>I have the change for you: You have 12 dollars, 0 quarters, 0 dimes, 1 nickels, and 4 pennies.

>

>You can provide change as follows:

>

> dollar : 12

>

> quarter : 0

>

> dime : 0

>

> nickel : 1

>

> penny : 4

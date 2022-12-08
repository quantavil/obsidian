# INDEX

- [[#if / else statement|if / else statement]]
- [[#Switch Statement|Switch Statement]]
	- [[#Switch Statement#Enumeration|Enumeration]]
- [[#Ternary Operator|Ternary Operator]]
- [[#For loop|For loop]]
- [[#Ranged Based for Loop|Ranged Based for Loop]]
- [[#While loop|While loop]]
- [[#The Do/While loop|The Do/While loop]]
- [[#Break and Continue|Break and Continue]]
	- [[#Break and Continue#Break vs Return|Break vs Return]]
	- [[#Break and Continue#Continue|Continue]]
- [[#Nested Loops|Nested Loops]]
- [[#Section Challenge|Section Challenge]]


---
## if / else statement
A compound statement (also called a block, or block statement) is a group of zero or more statements that is treated by the compiler as if it were a single statement.
Blocks begin with a { symbol, end with a } symbol, with the statements to be executed being placed in between. Blocks can be used anywhere a single statement is allowed. No semicolon is needed at the end of a block.
The variable are visible only within the block - local scope.

```cpp
[[include]] <iostream>
using namespace std;
int main ()
{
 int score {};
 cout << "Enter your score: ";
 cin >> score;
 if (score >= 90)
 // This is the nested statement
 {if (score >= 100 )
 cout << "You have entered an invalid score.";
 else if (score >= 95)
 cout << "You have a A+ grade.";
 else
 cout << "You have a A grade.";
 }
 else if (score >= 80)
 cout << "B";
 else if (score >= 70)
 cout << "C";
 else if (score >= 60)
 cout << "D";
 else
 if (score < 0)
 cout << "You have entered an invalid score.";
 else
 cout << "F";
 cout << "\nDone" << endl;
 return 0;
}
```

>[!Output]
>Enter your score: 67
>D
>Done
---


## Switch Statement

![img8](img/img8.png)
```cpp
[[include]] <iostream>
using std::cout;
using std::endl;
using std::cin;
int main()
{
 char letterGrade {}; // integral type
 cout << "Enter a letter grade: ";
 cin >> letterGrade;
 switch (letterGrade)
 {
 case 'A':
 case 'a':
 cout << "Excellent!" << endl;
 break;
 case 'B':
 case 'b':
 cout << "Good job!" << endl;
 break;
 case 'C':
 case 'c':
 cout << "You can do better!" << endl;
 break;
 case 'D':
 case 'd':
 {
 char confirm {}; // if you want to declare a variable inside a switch statement, you must use braces
 cout << "Are you Sure Y/N ? : ";
 cin >> confirm;
 if (confirm == 'Y' || confirm == 'y')
 cout << "Geuss You didn't Study!" << endl;
 else if (confirm == 'N' || confirm == 'n')
 cout << "You can do better!" << endl;
 else
 cout << "Invalid Input!" << endl;
 }
 break;
 default :
 cout << "Invalid grade!" << endl;
 }
}
```

>[!Output]
>Enter a letter grade: d
>Are you Sure Y/N ? : n>
>You can do better!


### Enumeration
**Enumeration** is a user defined datatype in C/C++ language. It is used to assign names to the integral constants which makes a program easy to read and maintain. The keyword “enum” is used to declare an enumeration.
```cpp
[[include]] <iostream>
using namespace std;
enum colors{red=5, black};
enum suit{heart, diamond=8, spade=3, club};
int main() {
 cout <<"The value of enum color : "<<red<<","<<black;
 cout <<"\nThe default value of enum suit : "<<heart<<","<<diamond<<","<<spade<<","<<club;
 return 0;
}
```

>[!Output]
>The value of enum color : 5,6
>The default value of enum suit : 0,8,3,4


```cpp
[[include]] <iostream>
using namespace std;
int main() {
 enum Direction {
 left,right,up,down
 };
 Direction head {left};
 switch (head) {
 case left:
 cout << "left";
 break;
 case right:
 cout << "right";
 break;
 case up:
 cout << "up";
 break;
 case down:
 cout << "down";
 break;
 default:
 cout << "Ok";
 }
}
```

>[!Output]
> left


## Ternary Operator

```cpp
[[include]] <iostream>
using namespace std;
int main ()
{
 int num{};
 cout << "Enter a number: ";
 cin >> num;
 cout << num << " is " << ((num %2 == 0) ? "Even" : "Odd") << endl;
 int num1{} , num2{};
 cout << "Enter two numbers: ";
 cin >> num1 >> num2;
 cout << "The numbers are " << ((num1 != num2) ? "not same" : "same") << endl;
 return 0;
}
```
> [!Output]
> Enter a number: 68
> 68 is Even

![img9](img/img9.png)


## For loop
When you know exactly how many times you want to loop through a block of code, use the for loop instead of a while loop:

```cpp
[[include]] <iostream>
using namespace std;
int main ()
{ 
 // for loop initalization style
 for (int i {1}; i < 10; i++)
 {
 cout << i << " ";
 }
 cout << endl;
 // for loop assignment style
 for (int i = 2; i < 10; i++)
 {
 cout << i << " ";
 }
 cout << endl;
 // intizating i first
 int i {3};
 for (; i < 10; i++)
 {
 cout << i << " ";
 }
 cout << endl;
 // you can also write as ---------------
 for (i = 4 ; i < 10; i++)
 {
 cout << i << " ";
 }
 cout << endl;
}
```

> [!Output]
> 1 2 3 4 5 6 7 8 9
> 2 3 4 5 6 7 8 9
> 3 4 5 6 7 8 9
> 4 5 6 7 8 9


Since loop expression are optional, it is possible to have no initilization , no test , and no increment\
Example of infinite loop
```cpp
for (; ;) {
 cout << "Hello, world!" << endl;
 }
```
```cpp
[[include]]<iostream>
using std::cout;
using std::endl;
int main()
{ 
 // comma operator
 for (int i {1}, j{15}; i <=5 ,i*j <= 30; ++i, j -= 2) // you can use any number of test condition and also use "and" operator instead of comma "," only in test condition
 { 
 cout << i << "*" << j << " = "<<i*j << endl;
 }
 return 0;
}
```

>[!Output]
>1*15 = 15
>2*13 = 26


```cpp
[[include]]<iostream>
using std::cout;
using std::endl;
int main()
{ 
 int n {1};
 for (;n<101;n++)
 {
 cout << n <<((n % 10 ==0) ? "\n" : " ");
 }
 return 0;
}
```

> [!Output]
> 1 2 3 4 5 6 7 8 9 10
> 11 12 13 14 15 16 17 18 19 20
> 21 22 23 24 25 26 27 28 29 30
> 31 32 33 34 35 36 37 38 39 40
> 41 42 43 44 45 46 47 48 49 50
> 51 52 53 54 55 56 57 58 59 60
> 61 62 63 64 65 66 67 68 69 70
> 71 72 73 74 75 76 77 78 79 80
> 81 82 83 84 85 86 87 88 89 90
> 91 92 93 94 95 96 97 98 99 100


Extracting numbers from the vector using for loop
```cpp
[[include]]<iostream>
[[include]]<vector>
using namespace std;
int main()
{ 
 vector<int> nums{10,20,30,40,50};
 for(int i {0}; i < nums.size(); i++)
 {
 cout << nums[i] << endl;
 }
 return 0;
}
```

>[!Output]
>10
>20
>30
>40
>50


## Ranged Based for Loop

```
# SYNTAX

for ( range_declaration : range_expression )
	loop_statement
```


**Parameters :**
range_declaration : a declaration of a named variable, whose type is the type of the element of the sequence represented by range_expression, or a reference to that type. Often uses the auto specifier for automatic type deduction.

range_expression : any expression that represents a suitable sequence or a braced-init-list.
loop_statement : any statement, typically a compound statement, which is the body of the loop.

```cpp
[[include]] <iostream>
[[include]] <vector>
[[include]] <iomanip>
using namespace std;
int main() {
 // Iterating over whole array
 vector<int> v = {1, 2, 3, 4, 5};
 for (int i : v) {
 cout << i << " ";
 }
 cout << endl;
 // Iterating over array with index
 for (auto n : {0,1,2,3,4,5}) { 
 cout << n << " ";
 }
 cout << endl;
 // Iterating over array
 int arr[] = {1, 2, 3, 4, 5};
 for (auto n : arr) // type is auto, so number has its type deduced from the arr
 cout << n << ' ';
 cout << endl;
 // just looping over array
 for (int n : arr)
 cout << "I'm in loop ......" << ' ';
 cout << endl;
 // printing string from letters
 string s = "Hello";
 for (char c : s)
 cout << c << ' ';
 // looping over a vector
 vector<double> temp {87.9,77.8,88.0,72.5};
 double total {};
 double avg {};
 for (auto i : temp)
 total += i;
 if(temp.size() != 0)
 avg = total/temp.size();
 cout << fixed << setprecision(1);
 cout << "Average temperature is "<< avg << endl;
 // filtering spaces
 for (auto c : "This is a test")
 if (c != ' ') // not work with " " because c is char ' ' and " " is string
 cout << c ;
 cout << endl;
 // printing tab
 for (auto d : "This is a test with tabs")
 if (d == ' ') 
 cout << "\t" ;
 else
 cout << d ;
 return 0;
}
```

> [!Output]
> 1 2 3 4 5
> 0 1 2 3 4 5
> 1 2 3 4 5
> I'm in loop ...... I'm in loop ...... I'm in loop ...... I'm in loop ...... I'm in loop ......
> H e l l o Average temperature is 81.5
> Thisisatest
> This    is      a       test    with    tabs


## While loop
The while loop loops through a block of code as long as a specified condition is true

```cpp
[[include]] <iostream>
using std::cout;
using std::endl;
using std::cin;
int main() {
 int num {};
 cout << "Enter a number: ";
 cin >> num;
 int i {0};
 while (num > i) {
 cout << i << endl;
 i++;
 }
 // valid number
 int number {};
 cout << "Enter a number less than 10 but greater than 0: ";
 cin >> number;
 while (number > 10 || number < 1) {
 cout << "Invalid number. Try again: ";
 cin >> number;
 }
 cout << "The number is: " << number << endl;
 // using flag
 bool done {false};
 int number2 {};
 while (!done) {
 cout << "Enter a number less than 10 but greater than 0: ";
 cin >> number2;
 if (number2 > 10 || number2 < 1) {
 cout << "Invalid number. Try again: ";
 cin >> number2;
 } else {
 cout << "Thanks" << endl;
 done = true;
 }
 }
 return 0;
}
```

> [!Output]
> Enter a number: 6
> 0
> 1
> 2
> 3
> 4
> 5
> Enter a number less than 10 but greater than 0: 7
> The number is: 7
> Enter a number less than 10 but greater than 0: 99
> Invalid number. Try again: 66
> Enter a number less than 10 but greater than 0: 6
> Thanks


## The Do/While loop

The do/while loop is a variant of the while loop. This loop will execute the code block once, before checking if the condition is true, then it will repeat the loop as long as the condition

```cpp
[[include]] <iostream>
using namespace std;
int main() {
 char c{};
 do {
 cout << "\n--------------------" << endl;
 cout << "1. Do this" << endl;
 cout << "2. Do that" << endl;
 cout << "3. Do Something else" << endl;
 cout << "Q. Quit" << endl;
 cout << "\n Enter your selection: ";
 cin >> c;
 switch (c) {
 case '1':
 cout << "\nYou selected 1" << endl;
 break;
 case '2':
 cout << "\nYou selected 2" << endl;
 break;
 case '3':
 cout << "\nYou selected 3" << endl;
 break;
 case 'Q':
 case 'q':
 cout << "\nGoodbye" << endl;
 break;
 default:
 cout << "\n Invalid selection" << endl;
 break;
 }
 } while (c != 'q' && c != 'Q'); //here we are using the logical operator '&&' because we are using '!=' which mean if we pass either q or  Q it will give (false && true) = false and the while loop will stop
 return 0;
}
```

>[!Output]
> 1. Do this
>2. Do that
>3. Do Something else
>Q. Quit
>
> Enter your selection: w
>
> Invalid selection
>
>--------------------
>1. Do this
>2. Do that
>3. Do Something else
>Q. Quit
>
> Enter your selection: q
>
>Goodbye


## Break and Continue
In the context of a `switch statement`, a `break` is typically used at the end of each case to signify the case is finished : <span style="color:cyan"> (*which prevents fallthrough into subsequent cases*) text</span>.

```cpp
case '+':
 std::cout << x << " + " << y << " = " << x + y << '\n';
 break; // don't fall-through to next case
```

In the context of a `loop`, a `break` statement can be used to end the loop early. Execution continues with the next statement after the end of the loop

```cpp
[[include]] <iostream>
int main()
{
 while (true) // infinite loop
 {
 std::cout << "Enter 0 to exit or any other integer to continue: ";
 int num{};
 std::cin >> num;
 // exit loop if user enters 0
 if (num == 0)
 break;
 }
 std::cout << "We're out!\n";
 return 0;
}
```


### Break vs Return

**Break vs Return** : A break statement terminates the switch or loop, and execution continues at the first statement beyond the switch or loop. A return statement terminates the entire function that the loop is within, and execution continues at point where the function was called.

```cpp
[[include]] <iostream>
using std::cin;
using std::cout;
using std::endl;
int breakOrReturn() {
 while (true) // infinite loop
 {
 cout << " Enter b to break and r to return : ";
 char ch;
 cin >> ch;
 if (ch == 'b')
 break; // execution will continue at the first statement beyond the loop
 if (ch == 'r')
 return 1; // return will cause the function to immediately return to the caller (in this case, main())
 }
 cout << "We broke out of loop";
 return 0;
}
int main() {
 int result {breakOrReturn()};
 cout << "Result is " << result << endl;
 return 0;
}
```

> [!Output]
> Enter b to break and r to return : b
> We broke out of loopResult is 0
>Enter b to break and r to return : q
>Enter b to break and r to return : r
> Result is 1


### Continue

**Continue** : The continue statement provides a convenient way to end the current iteration of a loop without terminating the entire loop.

```cpp
[[include]] <iostream>
int main()
{
 for (int count{ 0 }; count < 10; ++count) {
 // if the number is divisible by 4, skip this iteration
 if ((count % 4) == 0) {
 continue; // go to next iteration
 }
 // If the number is not divisible by 4, keep going
 std::cout << count << '\n';
 // The continue statement jumps to here
 }
 return 0;
}
```


## Nested Loops

```cpp
[[include]] <iostream>
using namespace std;
int main() {
 for (int i{1} ; i < 11 ; ++i) { // outer loop also colled slow loop
 for (int j{1} ; j < 11 ; ++j) { // inner loop also called fast loop
 cout << i << " * " << j << " = " << i * j << '\n';
 }
 cout << "-------------------\n";
 }
 return 0;
}
```

> [!Output]
> 2 * 1 = 2
> 2 * 2 = 4
> 2 * 3 = 6
> 2 * 4 = 8
> 2 * 5 = 10
> 2 * 6 = 12
> 2 * 7 = 14
> 2 * 8 = 16
> 2 * 9 = 18
> 2 * 10 = 20
> -------------------
> 3 * 1 = 3
> 3 * 2 = 6
> 3 * 3 = 9
> 3 * 4 = 12
> 3 * 5 = 15
> 3 * 6 = 18
> 3 * 7 = 21
> 3 * 8 = 24
> 3 * 9 = 27
> 3 * 10 = 30
> -------------------
> 4 * 1 = 4
> 4 * 2 = 8
> 4 * 3 = 12
> 4 * 4 = 16
> 4 * 5 = 20
> 4 * 6 = 24
> 4 * 7 = 28
> 4 * 8 = 32
> 4 * 9 = 36
> 4 * 10 = 40
> -------------------
> 5 * 1 = 5
> 5 * 2 = 10
> 5 * 3 = 15
> 5 * 4 = 20
> 5 * 5 = 25
> 5 * 6 = 30
> 5 * 7 = 35
> 5 * 8 = 40
> 5 * 9 = 45
> 5 * 10 = 50
> -------------------


```cpp
[[include]] <iostream>
[[include]] <vector>
using namespace std;
int main() {
 cout << "How may data item you want to enter? ";
 int n;
 cin >> n;
 vector <int> data{};
 for (int i{1}; i <= n; i++) {
 int data_item{};
 cout << "Enter data item " << i << ": ";
 cin >> data_item;
 data.push_back(data_item);
 }
 // displaying data in form of histogram
 for (auto val: data) {
 for (int i{0}; i < val; i++) {
 if (i % 5 == 0) {
 cout << "*";
 }
 else {
 cout << "-";
 }
 }
 cout << endl;
 }
 return 0;
}
```

>[!Output]
>How may data item you want to enter? 4
>Enter data item 1: 23
>Enter data item 2: 12
>Enter data item 3: 1
>Enter data item 4: 56
>*----*----*----*----*--
>*----*----*-
>*----*----*----*----*----*----*----*----*----*----*----*



## Section Challenge

```cpp
[[include]] <iostream>
[[include]] <vector>
using namespace std;
int main () {
 vector<int> list{};
 char choice {};
 int num {};
 do {
 cout << "\nTo print the list, enter P.\n";
 cout << "To add an element, enter A.\n";
 cout << "To delete an element, enter D.\n";
 cout << "To find the mean of the list, enter M.\n";
 cout << "To find the Smallest number in list, enter S.\n";
 cout << "To find the Largest number in list, enter L.\n";
 cout << "To Quit , enter Q.\n";
 cout << "\nEnter your choice: ";
 cin >> choice;
 int sum {};
 int smallest {};
 int largest {};
 switch (choice)
 {
 case 'P':
 case 'p':
 if (list.size() != 0) {
 cout << "[";
 for (int i = 0; i < list.size(); i++) {
 cout << list[i] << " ";
 }
 cout << "]" << endl;
 } else {
 cout << "[]- The list is empty.\n";
 }
 break;
 case 'A':
 case 'a':
 cout << "\nEnter the number to be added: ";
 cin >> num;
 list.push_back(num);
 break;
 case 'D':
 case 'd':
 cout << "\nEnter the position at which number to be deleted: ";
 cin >> num;
 list.erase(list.begin() + num);
 break;
 case 'M':
 case 'm':
 if (list.size() != 0) {
 for (int i = 0; i < list.size(); i++) {
 sum += list[i];
 }
 cout << "The mean is: " << static_cast<double>(sum) / list.size() << endl;
 } else {
 cout << "The list is empty.\n";
 }
 break;
 case 'S':
 case 's':
 for (auto i : list) {
 if (i < smallest) {
 smallest = i;
 }
 }
 cout << "The smallest number in the list is: " << smallest << endl;
 break;
 case 'L':
 case 'l':
 for (auto i : list) {
 if (i> largest) {
 largest = i;
 }
 }
 cout << "The largest number in the list is: " << largest << endl;
 break;
 default:
 cout << "Invalid choice.\n";
 break;
 }
 } while ((choice != 'Q') && (choice != 'q'));
 return 0;
}
```

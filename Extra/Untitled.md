starting with the first question that is
what is the difference between c
and c plus plus now c language is a
processor oriented language
whereas c plus plus is partially
object-oriented language
because it doesn't support object
oriented features completely
c language supports top-down approach
and c-plus plus supports a bottom-up
approach
here the bottom-up approach means the
development of modules
in c splits starts from the bottom
c doesn't support function or operator
overloading
whereas c plus supports both function
and operator overloading
c language doesn't support virtual and
friend function
c plus plus language supports both
virtual and friend function
c language has 32 keywords whereas c
plus has 52 keywords
next question is what are classes and
objects in c
plus a class is a user-defined data type
that contains data members and member
functions it is defined with keyword
class
objects are defined as an instance of a
class
once the object is created then it can
operate on both
data members and member functions
coming to the third question that is
what
are access modifiers
access modifiers are used to define
accessibility
for the class members it defines
how the members of the class are
accessed outside the class scope
there are three types of access
modifiers that is private
public and protected let's start with
private
the members who are declared as private
cannot be accessed
directly from outside the class they can
only be accessed by the member functions
inside the class now public
the members who are declared as public
can be accessed from within the class
as well as outside the class and even
from
outside the package as well
now protected the members who are
declared as protected
can be accessed from within the class
and from the derived class
now coming to the next question that is
what is
c plus plus oops concept oops stands for
object oriented programming there are
some concepts
of oops that is object
class inheritance polymorphism
encapsulation
and abstraction now let's understand
these concepts
let's start with object an object is a
basic unit
of object oriented programming it can be
defined as an instance of a class
we can create multiple objects of a
class
now class is a template of an object
it is user defined which holds member
functions and data members
the data and code which is defined
inside the class
are said to be the members of the class
now inheritance inheritance can be
defined as a process
in which child class inherits all the
properties and behavior of its parent
class
the class which is inherited is called
the base class
and the class which inherits is called
the derived class
now polymorphism polymorphism is the
ability to give different meanings to
the same function
it allows us to redefine a function and
create it with a completely new
definition
now encapsulation encapsulation means
binding code and data together
into a single unit now

now coming to the next question that is
what is the difference between
a while loop and a do-while loop
so first is while loop while loop
verifies the condition
if it's true then it iterates the loop
till the condition becomes false
on the other side do while loop first
iterates the loop body once
then it checks for the condition
in while loop the syntax is while
keyword
then condition inside the brackets
the syntax of do while loop is due block
and after that while keyword with a
condition
in the while loop if the condition
is false then not a single statement
will execute inside the loop on the
other hand
in do while loop if the condition is
false
then also the body will execute once
now coming to the sixth question
that is what is a constructor
a constructor can be defined as a member
function
that is invoked whenever we create an
object
it has the same name as that of class
there are two types of constructors in c
plus
that is default constructor and
parameterized constructor
default constructor are those
constructors which do not take any
parameters
if we don't define any constructor then
the compiler will automatically provide
a default constructor
on the other hand parameterized
constructor are those constructors
in which we can pass the arguments
now coming to the next question
which of the following operator cannot
be overloaded
our options are a subtraction operator
b addition operator c ternary operator
and d modulo operator
so our correct answer is
c ternary operator because overloading
this operator
is not syntactically possible so let's
move on to our next question
write a program to find the factorial of
a number
so here we have to write a program of
factorial
in which we will enter a number and its
factorial is displayed on the screen
so here we have declared an integer n
which will take an input from the user
and another variable fact which we have
initialized as one
after that we have displayed a message
enter a positive integer and we have
taken
an input of the integer now
if the number or integer entered by user
is less than 0 that is in the negative
then it will display error as there is
no factorial of negative number
and all the positive number will go to
the else block
inside the else block we have used for
loop
and it is iterating from 1 to n that is
the number users had
entered and inside the for loop
it is written fact into equal to i
which can also be written as fact equal
to
fact into i which means one by one
all the numbers from 1 to n will be
multiplied by fact
variable and the result will be stored
in the fact variable itself once the
iteration is done
then the fact variable where the result
is stored is displayed
so this is the factorial program
now coming to the ninth question that is
what is operator overloading operator
overloading is a mechanism
in which we provide an additional
meaning to the operators
in this an operator is overloaded to
give
user defined meaning for example
we can overload an addition operator in
a class like string
to concatenate two strings by only using
addition sign now
our next question is what if we compile
a program
without the main function now another
question arises
is it possible to compile a program
without the main function
so the answer is yes we can compile a
program
without the main function but we cannot
run or execute the program
because the main function is the entry
point from where all the execution
begins
and without the entry point the program
is not executable
so we can compile the program but we
cannot run it without the main function
now moving to the next question
what is operator overloading and
function overloading
as we have already discussed operator
overloading
operator overloading allows operators to
have an extended meaning
apart from their predefined meaning
function overloading on the other hand
defines a method
in such a way that there are multiple
ways to call them
now our next question is what is the
difference between
equal to operator and assignment
operator
the equal to operator checks whether two
values
are equal or not if equal
then it's true otherwise it will return
false
the assignment operator on the other
hand assigns the value
of right variable to the left variable
coming to the 13th question that is
when void return type is used
void return type is used when we don't
want to return any value
it specifies that the function doesn't
return a value
function with void return type completes
its task
and then returns the control to the
caller
so our next question is what is call by
value
and call by reference in c plus plus
first of all both of these methods that
is call by value and call by reference
are the methods to pass the values to
the functions
so let's start with the first method
that is call by value method
in call by value method we pass the
copies of actual parameters to the
function's formal parameters
this means if there is any change in the
values inside the function
then that change will not affect the
actual values
in call by reference method the
reference or
address of actual parameters is sent to
the function's formal parameters
this means any change in the values
inside the function
will be reflected in the actual values
because here we are sending the address
of the values coming to the 15th
question
that is what is inline function
the inline function is expanded in line
when it's called when this function is
called
the whole code of inline function gets
inserted
or substituted at the inline function
call
or in other words the compiler replaces
the function calling location
with the definition of the inline
function at compile time
its syntax is the inline keyword
return type and function name and
parameters inside the brackets
coming to the next question that is what
are pointers in c
plus pointers are the variables
that holds the memory address of another
variable
the type of variable must correspond
with the type of pointer
for example the pointer of character
type can hold the address of character
type variable
and the same goes for integer and other
data types
its syntax is type of variable and
as to 6 sign with the name of pointer
moving to the next question that is what
is scope resolution operator
a scope resolution operator is
represented as
shown this operator is used to associate
function
definition to a particular class
this operator is used for the following
purposes to access
a global variable when we have a local
variable with same name
second is to define a function outside
the class
now moving to the next question and this
question is
output based question so the question is
what is the output of the following c
plus plus program so in this question we
have to determine the output of the
following
program and we have to select the
correct answer from the following
options
so in this program as we can see two
variables i
and x are initialized as 0 and after
that
do block is there and we know that do
block
executes for once regardless of any
condition
and inside the do block there is if
statement in which the condition
is if i mode equal to 0
then only the block will execute so if i
is initially 0 and we know 0 mode 5
is 0 so the condition is satisfied and
it will display
0 as the value of x
x is 0 initially after that the value is
incremented
for both i and x now the value of i
is 1 and 1 mode five is one
so it doesn't satisfy the condition so
the value of i will increment again and
similarly the process will repeat
for two mode five three mode five
four mode five but five mode five
is zero so the value of x here
which is one now will be displayed and
increments to two then afterwards
i becomes six then 7 then 8 the 9
on incrementing but doesn't meet the
condition at that time
but when it becomes 10 the control will
move
outside the loop and 2 will be displayed
so our answer becomes 0 1 and 2.
so this is our answer 0 1 2
now let's move on to the next question
so this question is a multiple choice
question and in this question we have to
determine the size of
integer data type so our options are 4
bytes
1 byte 8 bytes and 2 bytes
so our answer is 4 bytes
4 bytes is the size of integer data type
so now let's move to the next question
this question is what is std in c
plus first option is std is standard
class in c
plus plus std is standard file reading
header in c
plus std is a standard header file
then last option is std is standard
namespace in c
plus so our correct answer is
std is a standard namespace in c plus
it is used in programs while writing
using namespace standards
and it tells the compiler to take
everything
in standard namespace so let's move on
to the next question
so in this question we have to tell how
to input a string
in c plus with spaces now we all know
how to input
a string in c plus plus without spaces
because it's quite easy
but let's understand how to do it with
spaces
so in this question as you can see there
is a string
that we have declared s the name of the
string is s
after that we have displayed a message
enter the sentence with spaces
and then we are taking the input here
get line is the member function of i
stream class
which is used to read the string with
spaces
so as we can see get line after that in
the bracket
c in which is used to take the input
after that the name of the string
that is s and after that we have
displayed
the string name that is s so this is how
we can take the input from the user with
spaces
using this get line function so let's
move to our next question
that is what is the difference between
new and malloc
now both of these are used to allocate
memory
so let's start with new new is an
operator
whereas malloc is a function the new
operator
calls the constructor on the other hand
malloc function
doesn't call the constructor in case of
new
there is no need to specify memory size
while using new operator
in case of malloc we have to specify the
memory size
in malloc function new operator
can be overloaded whereas malloc
function
can never be overloaded
now next question is what is the
difference between
prefix and postfix
in prefix first the value is incremented
and then the value is assigned to the
expression
but in case of postfix the value is
assigned to the expression
and then the variable's value is
implemented
now coming to the next question
that is what is the output of the below
c plus plus program
so as we can see the program this is the
program of enumeration
as you can see the enum keyword so here
three enum variables are there that is
blue green and great
and we know that there are some default
values that are
assigned to the enum variables that
starts from zero
but we also know that we can change
these default values
so as you can see in this question green
equals five
so green's value is five
and we can see the element grade
has no value so in enum if this case
arises then the value of the next
element would be one greater than
its previous element so ultimately the
value of
grate element would be six
so as you can see here we have printed
blue
and great so our output would be
0 and 6 that means the value of blue
is 0 and the value of great is 6.
so now let's move on to the next
question
in this question we have to find the
frequency of a number
in c plus plus so as you can see in the
program we have given this number
one three three two four two two five
two three and we have to find the
frequency of the number
2 that is k equals to 2 k is the number
so in this program first of all we'll
pass
both of these values to a function named
frequency
now inside that function we have
declared a counter variable c and
initialized
it with 0. now after that we have used
while loop
and inside the while loop we have put
the condition num
greater than zero now it means the loop
will execute
till the value of num is greater than
zero
now after that inside the while loop we
have put
an if statement condition that is num
mod 10 equals k now keep in mind that
k is the number which we want to find
the frequency of
that is 2 now
num mod 10 we know that any number
when mod with 10 gives the last digit of
that number
so one by one all the digits of this num
variable will be checked
starting from 3 then 2 then 5
then 2 then again 2 then 4 similarly
goes on
so one by 1 all of these digits
will be checked with the value of k that
is 2
and if the digit matches with k
then that counter variable which we have
initialized as 0
will increment and
after that num equals to num divided by
10
will delete that last element so that
the repetition of digits
don't occur so this is how we can find
the frequency of a number
in c plus plus so now let's move on to
the next question
which of the following statement is
correct about the program given below
this is again an output based question
so let's have a look at the program
and these are its options 7 14
0 and 1 so we have to select one out of
it
so in this program we can see a variable
x is declared and a pointer p
is there and we have assigned this
value 7 to the variable x
after that we are storing the memory
location of x
to this pointer p and at last we are
displaying the output
using the d reference operator as we
know that if we want to display
the value at an address then we use d
reference operator
so our output would be 7 as the
value at that memory location is 7.
now let's move on to the next question
which of the following statement is
correct about the program given below
now in this question again we have to
determine the output
so let's have a look at the program as
you can see
there are three variables x y
and z and we have initialized them 2
4 and 5 respectively and after that we
are calling a function
duplicate and we are passing the values
but in this case we are passing the
values as reference
so this is the case of call by reference
and we know in case of call by reference
the actual value of the variable also
changes
so here in this question we are passing
the values as reference
to this function named duplicate
now inside this function we can see that
every variable
each of these three variables is getting
multiplied by 2.
so in case of call by value there will
be no change in the actual value
but here we are not passing the
arguments as call by value
but we are passing it as call by
reference
so the changes will be reflected in the
actual value
so when 2 is multiplied by 2 it gives
you 4
and 4 is multiplied by 2 is it will give
you 8
and when 5 multiplied by 2 it will give
you 10
so its output would be 4 8
and 10. now let's move on to the next
question how to write a program
to check if the number is palindrome or
not
so palindrome is a number that remains
the same when its digits are reversed
so here we have to write the program to
check if the number
is palindrome or not so before moving
forward
there are two things that you should
keep in mind that
if a number is mod by
10 that is number mod 10 it will give
the last digit of that particular number
for example if there is a number 123
then 123 mod 10 will give you 3
and if we divide that number by 10
then that will remove the last digit
for example 123 divided by 10
will give you 12 as an answer
so now let's have a look at this
question inside the int main
there are variables like num digit
reverse
and n and after that there is a message
saying enter a positive number
after that we are taking the input num
and we are storing that num variable
inside another variable that is
n we'll talk about this later why we are
storing this to another variable
n now there's a do block
inside the do block we can see digit
equals
num mode 10 now to understand this let
us take an example as
let us suppose the number to be 123 now
num is that number and we know that
123 mod 10 equals to 3
that means the last digit of that number
so now digit is storing the last digit
of that number
after that we can see reverse equals to
reverse into 10
plus digit now we know that reverse we
have initialized as 0
so reverse equal to 0 plus 3
now reverse now becomes equal to 3
after that we can see in the next line
num equals to num
divided by 10 that means 123 divided by
10
and as we have already discussed 123
divided by
10 will give you 12. now
now this 12 will again go to num mode 10
and the value of digit now will become 2
now this 2 will be added in the second
line as we can see
and reverses 3 as we know now 3 into 10
becomes 30
plus digit which is now 2 that becomes
32
and after that line num equals to num
divided by 10 will remove that
2 from the 12 so now the value of num
is 1 now again the num will
go to num mode 10
one more time gives you one so now the
value of digit is one
and in the next line reverse value is
now
32 so 32 into 10 becomes 320
after that we will add the value of
digit that is equal to 1
so it will become 320 plus 1 that will
give you 321
so after that the condition of while
loop
terminates and after that we can see
the reverse of the number is rev
reversed
because the result is stored at this
variable
now i'll tell you why we have stored num
into the variable n because we don't
want to make changes
with the num variable that is the user
input
and here we have used if condition and
inside the if condition all we have
written is
if the value that is entered by the user
is equal to the reverse of that
particular value
then that number is a pallid rom else
the number is not a palindrome
now coming to the next question which of
the following
will give the size of object or type
so the right answer is the size of
operator gives the size of object
or type now let's move on to the next
question
which of the following is not a member
of class
so the answer is among the following
friend function
is not the member of a class
now let's move on to 31st question
that is what is stl
stl stands for standard template library
it is a library container
that provides generic classes and
functions
stl components are containers algorithms
iterators and function objects
so next question is what is a friend
function
a friend function can be defined as a
function that can
access private public and protected
member of the class
the friend function is declared using
the front keyword
this function is declared inside the
class
now next is what is a copy constructor
a copy constructor is a member function
that initialize
an object using another object within
the same class
the constructor is of two types default
copy constructor and user defined copy
constructor
now let's move on to the next question
how does the strings are stored in the
memory
options are sequence null non-contiguous
contiguous
so the correct answer is the characters
of strings are stored
contiguously in the memory
moving to the next question what is
inheritance
inheritance is the mechanism in which we
can create a new class that is child
class
from the existing class that is parent
class
this child class is also known as
derived class and the parent class is
also called
base class and in the inheritance
child class inherits properties and
behavior from its parent class
so our next question is what is
abstraction abstraction can be defined
as a technique
in which we only show the functionality
to the user
that is the details that we want the
user to
see and hiding the internal details or
implementation details
which is not necessary for a user to see
now let's move on to our next question
what is the output of the below code so
here we can see
they have used ternary operator in this
question
so first of all as we can see there are
three variables a b
and c and five and six are the values of
a and b
that have been assigned to them and at
line 11 we can see a
greater than b question mark a colon
b so this is a ternary operator
here a greater than b is the test
expression if this
test expression is true then
the expression after the question mark
that is a will be the answer
and if it is false then the expression
after colon that is b will be the answer
that means if a is greater than b
then a will be the answer and if a is
not
greater than b then b will be the answer
and as you can see the value of a is 5
and the value of b
is 6 so the test expression is false
so that means b will be the answer so
now the value of c
is b that is 6
so our correct answer is 6.
now let's move on to the next question
what among these is used to return the
number of characters in the string
option a is size option b is length
c is both size and length and option d
is name
so the answer is both size and length
will return the number of characters in
the string
now let's move to the 39th question
what is the output of the below code as
we can see in this code the value of j
is 10 then the value of j is incremented
as you can see in the line 10 j plus
plus
so the value of j is incremented to 11.
after that
j is at d 200 and at last
j is added to 999 which will give us the
result as
1010 that is 10 10
and this value is being assigned to i so
our answer is 10 10. now
let's move to the next question that is
the last question
pick the correct statement about string
objects in c
plus plus option a is string objects
must be terminated by a null character
option b is string objects have static
size
option c is string objects have a
dynamic size
option d is string objects use extra
memory than required
so our correct answer is c
string objects have dynamic size they
are dynamic in nature
that is their size varies as their value
changes
so they don't use any extra memory so
these were some important c
plus interview questions
alright guys with that we have come to
the end of this session
i hope these interview questions will
help you in your preparation
if you like this video please give it a
thumbs up i hope it helped you all
thanks for watching stay safe and keep
learning
hi there if you like this video
subscribe to the simply learn youtube
channel
and click here to watch similar videos
to nerd up and get certified
click here

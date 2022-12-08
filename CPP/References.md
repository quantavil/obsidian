# References
>## size_t
>
>size_t is an - unsigned type. So, it cannot represent any negative values(<0).\
>You use it when you are counting something, and are sure that it cannot be negative.\
>For example, strlen() returns a size_t because the length of a string has to be at least 0.
>size_t is a type that can hold any array index.
>Depending on the implementation, it can be any of:
>- unsigned char
>- unsigned short
>- unsigned int
>- unsigned long
>- unsigned long long

>## string::npos
>
>std::string::npos
>static const size_t npos = -1;
>Maximum value for size_t
>npos is a static member constant value with the greatest possible value for an element of type size_t.
>This value, when used as the value for a len (or sublen) parameter in string's member functions, means "until the end of the string".
>As a return value, it is usually used to indicate no matches.

# [`<cstdlib> (stdlib.h)`](https://www.cplusplus.com/reference/cstdlib/)

**C Standard General Utilities Library**
This header defines several general purpose functions, including dynamic memory management, random number generation, communication with the environment, integer arithmetics, searching, sorting and converting.

# [`<cmath> (math.h)`](https://www.cplusplus.com/reference/cmath/)

**C numerics library**
Header `<cmath>` declares a set of functions to compute common mathematical operations and transformations:


**What is a buffer?**   
A temporary storage area is called a buffer. All standard input and output devices contain an input and output buffer. In standard C/C++, streams are buffered, for example in the case of standard input, when we press the key on the keyboard, it isn’t sent to your program, rather it is buffered by the operating system till the time is allotted to that program.

**How does it affect Programming?**   
On various occasions, you may need to clear the unwanted buffer so as to get the next input in the desired container and not in the buffer of the previous variable. For example, in the case of C after encountering “scanf()”, if we need to input a character array or character, and in the case of C++, after encountering the “cin” statement, we require to input a character array or a string, we require to clear the input buffer or else the desired input is occupied by a buffer of the previous variable, not by the desired container. On pressing “Enter” (carriage return) on the output screen after the first input, as the buffer of the previous variable was the space for a new container(as we didn’t clear it), the program skips the following input of the container.

**In the** **case of** [**C Programming**](https://www.geeksforgeeks.org/c/) 

-   C

## C

`#include<stdio.h>`

`int` `main()`

`{`

    `char` `str[80], ch;`

    `scanf``(``"%s"``, str);`

    `ch =` `getchar``();`

    `printf``(``"%s\n"``, str);`

    `printf``(``"%c"``, ch);`

    `return` `0;`

`}`

Input: 

```
GeeksforGeeks
a
```

Output: 

```
GeeksforGeeks
```

**In the** **case of** [**C++**](https://www.geeksforgeeks.org/c-plus-plus/) 

-   C++

## C++

`#include<iostream>`

`#include<vector>`

`using` `namespace` `std;`

`int` `main()`

`{`

    `int` `a;`

    `char` `ch[80];`

    `cin >> a;`

    `cin.getline(ch,80);`

    `cout << a << endl;`

    `cout << ch << endl;`

    `return` `0;`

`}`

Input: 

```
4
GeeksforGeeks
```

Output: 

```
4
```

In both the above codes, the output is not printed as desired. The reason for this is an occupied Buffer. The “\\n” character goes remains there in buffer and is read as the next input.

**How can it be resolved?**

**In the** **case of C :**  

**1\. Using “ while ((getchar()) != ‘\\n’); ”** : Typing “while ((getchar()) != ‘\\n’);” reads the buffer characters till the end and discards them(including newline) and using it after the “scanf()” statement clears the input buffer and allows the input in the desired container.

-   C

## C

`#include<stdio.h>`

`int` `main()`

`{`

    `char` `str[80], ch;`

    `scanf``(``"%s"``, str);`

    `while` `((``getchar``()) !=` `'\n'``);`

    `ch =` `getchar``();`

    `printf``(``"%s\n"``, str);`

    `printf``(``"%c"``, ch);`

    `return` `0;`

`}`

Input: 

```
GeeksforGeeks
a
```

Output: 

```
GeeksforGeeks
a
```

**2\. Using “ fflush(stdin) ”**: Typing “fflush(stdin)” after “scanf()” statement also clears the input buffer but use of it is avoided and is termed to be “undefined” for input stream as per the C++11 standards.

**In the** **case of C++ :**  

**1\. Using “ cin.ignore(numeric\_limits::max(),’\\n’); ”** :- Typing “cin.ignore(numeric\_limits::max(),’\\n’);” after the “cin” statement discards everything in the input stream including the newline. 

-   C++

## C++

`#include<iostream>`

`#include<ios>`    

`#include<limits>`

`using` `namespace` `std;`

`int` `main()`

`{`

    `int` `a;`

    `char` `str[80];`

    `cin >> a;`

    `cin.ignore(numeric_limits<streamsize>::max(),``'\n'``);`

    `cin.getline(str, 80);`

    `cout << a << endl;`

    `cout << str << endl;`

    `return` `0;`

`}`

Input: 

```
4
GeeksforGeeks
```

Output: 

```
4
GeeksforGeeks
```

**2\. Using “ cin.sync() ”:** Typing “cin.sync()” after the “cin” statement discards all that is left in the buffer. Though “cin.sync()” **does not work** in all implementations (According to C++11 and above standards). 

-   C++

## C++

`#include<iostream>`

`#include<ios>`    

`#include<limits>`

`using` `namespace` `std;`

`int` `main()`

`{`

    `int` `a;`

    `char` `str[80];`

    `cin >> a;`

    `cin.sync();`

    `cin.getline(str, 80);`

    `cout << a << endl;`

    `cout << str << endl;`

    `return` `0;`

`}`

Input: 

```
4
GeeksforGeeks
```

Output: 

```
4
```

**3\. Using “ cin >> ws ”:** Typing “cin>>ws” after “cin” statement tells the compiler to ignore buffer and also to discard all the whitespaces before the actual content of string or character array. 

-   C++

## C++

`#include<iostream>`

`#include<vector>`

`using` `namespace` `std;`

`int` `main()`

`{`

    `int` `a;`

    `string s;`

    `cin >> a;`

    `cin >> ws;`

    `getline(cin, s);`

    `cout << a << endl;`

    `cout << s << endl;`

    `return` `0;`

`}`

Input: 

```
4
GeeksforGeeks
```

Output: 

```
4
GeeksforGeeks
```

- >Use double quotes (`"y"` instead of `'y'`) for your strings, otherwise they are character literals. (Otherwise you will get Error : `warning: character constant too long for its type`)
- >What is the difference between initialization and assignment?
>**Ans: **Initialization gives a variable an initial value at the point when it is created. >Assignment gives a variable a value at some point after the variable is created.
- [[#C-style String|C-style String]]
- [[#C++  style String|C++  style String]]
	- [[#C++  style String#C++ Strings Functions|C++ Strings Functions]]
- [[#Section Challenge|Section Challenge]]


**Character Functions** : To use this we need to include `<cctype>` header file.
- Functions for testing characters
- Functions for converting characters case
![img10](./img/img10.png)
for character conversion function are:
- tolower()
- toupper()


## C-style String

![img11](./img/img11.png)
![img12](./img/img12.png)
![img13](./img/img13.png)
![img14](./img/img14.png)

To work with C-style string we need to include `<cstring>` header file./
Functions that we can use are:
- Copying
- Concatenation
- Searching
- Comparing

```cpp
[[include]] <iostream>
[[include]] <cstring> // for cstyle string functions
[[include]] <cctype> // for character based functions
[[include]] <typeinfo> // for typeid
using namespace std;
int main () {
 char first_name[20] {};
 char last_name[20] {};
 char full_name[40] {};
 cout << "Enter your first name: ";
 cin >> first_name;
 cout << "Enter your last name: ";
 cin >> last_name;
 // The strlen function returns the length of the string whose data type is size_t.
 cout << "Hello " << first_name << " length is " << strlen(first_name) << " and the type is " << typeid(43).name() << endl; // here j means unsigned integer and i means integer 
 cout << "Hello " << last_name << " length is " << strlen(last_name) << endl;
 cout << "--------------------------" << endl;
 strcpy(full_name, first_name); // copy first_name to full_name
 strcat(full_name, " "); // add a space to full_name
 strcat(full_name, last_name); // add last_name to full_name
 cout << "Your full name is " << full_name << endl;
 return 0;
}
```

>[!Output]
>Enter your first name: Karan
>Enter your last name: Rawat
>Hello Karanlength is 5 and the type is i
>Hello Rawatlength is 5
>-------------------------
>
>Your full name is Karan Rawat
---

```cpp
 cout << "Enter your full name: ";
 cin >> full_name; // The extraction operator stops at the first space
 cout << "Your first name is " << full_name << endl;
```

>[!Output]
>Enter your full name: Karan Rawat
>Your full name is Karan

```cpp
cout << "Enter your full name: ";
cin.getline(full_name, 40);
 cout << full_name << endl;
```

>[!Output]
>Enter your full name: Karan Rawat
>Karan Rawat


```cpp
[[include]] <iostream>
[[include]] <cstring> // for cstyle string functions
[[include]] <cctype> // for character based functions
using namespace std;
int main () {
 char full_name[40] {};
 char temp_name[40] {};
 // To read the full name in a single line, use cin.getline
 cout << "Enter your full name: ";
 cin.getline(full_name, 40);
 cout << full_name << endl;
 strcpy (temp_name, full_name);
 // The strcpy function copies the contents of the source string to the destination string.
 if (strcmp(temp_name, full_name) == 0) { // strcmp compares two strings and returns 0 if they are equal.
 cout << "The string is the same" << endl;
 } else {
 cout << "The string is different" << endl;
 }
 for (size_t i = 0; i < strlen(full_name); i++) {
 if (isalpha(full_name[i])) {
 full_name[i] = toupper(full_name[i]);
 }
 }
 cout << full_name << endl;
 if (strcmp(temp_name, full_name) == 0) {
 cout << "The string is the same" << "and the value of strcmp is " << strcmp(temp_name, full_name) << endl;
 } else {
 cout << "The string is different" << "and the value of strcmp is " << strcmp(temp_name, full_name) << endl;
 }
 return 0;
}
```
>[!Output]
>Enter your full name: KaraN Ra3AwAt
>KaraN Ra3AwAt
>The string is the same
>KARAN RA3AWAT
>The string is differentand the value of strcmp is 1


## C++  style String

- std::string is a class in the Standard Template Library (STL)
- `#include <string>`
- std namespace
- stored contigous in memory
- However unlike C-style string, it is not terminated by a null character.They are dynamic in nature and can grow as needed.
- Only C strings (char arrays which are intended for storing strings) had the null terminator.
- lots of useful functions are available in the string class
- our familiar operators can be used (e.g. +, +=, ==, !=, <, >, <=, >=, etc.)
 - It can compare:
 - two std::string objects
 - a std::string object and a C-style literal
 - a std::string object and a C++-style string variable
- string objects are mutable in C++  while in Python, Java , C# and other languages, they are immutable.
- can be eaisly converted to c-style string using `.c_str()`
- safer than C-style string since they provide methods for bound check


Declaring and initializing a string

```cpp
[[include]] <string>
using namespace std;
string s1 ; // empty string
string s2 {"Hello"}; // string with value "Hello"
string s3 {s2}; // copy constructor
string s4 = s2; // copy assignment
string s5 {"Hello",3}; // string with value "Hel"
string s6 {s3,1,3}; // string with value "ell"
string s7 (3,'a'); // string with value "aaa" // using pranthesis instead of {}
```


### C++ Strings Functions

```cpp
[[include]] <iostream>
[[include]] <string>
using namespace std;
int main () {
 string part1 { "C++" };
 string part2 { "is a powerful language" };
 // concatenation
 cout << "-- concatenation --" << endl;
 string sentence ;
 sentence = part1 + " " + part2;
 sentence += "!!!!!!!";
 cout << sentence << endl;
 //! sentence = "C++" + " is a powerful language"; // Illegal becaus you can't concatenate two c-style literals, you have to use strcat() function.
 // Accessing characters
 cout << sentence[0] << endl;
 cout << sentence.at(1) << endl; // at method is safer than [] because it throws an exception if the index is out of bounds
 // Assigning characters
 sentence[0] = 'Q';
 sentence.at(1) = '-';
 cout << "After assigning 'Q' at 0th and '-' at 1 : " << sentence << endl;
 // for loop
 cout << "\n--------looping--------" << endl;
 for (size_t i {0}; i < part1.length(); i++) {
 cout << part1[i] << endl;
 }
 //loop through the string
 cout << "\n--------range based for loop--------" << endl;
 for (char c : part1) {
 cout << c << endl;
 }
 // loop through the string but instead of using char using int
 for (int c : part1) {
 cout << c << endl;
 }
 // Comparing C++ strings lexically
 string s1 { "Apple"};
 string s2 { "Banana"};
 string s3 { "Kiwi"};
 string s4 { "apple"};
 string s5 { s1};
 cout << boolalpha;
 bool result = s1 == s2;
 cout << " s1 == s2 : "<< result << endl;
 cout << " Apple  == Apple  : " << (s1 == s5) << endl;
 cout << " Apple == apple : "<< (s1 == s4) << endl;
 cout << " Apple != Kiwi : "<< (s1 != s3) << endl;
 cout << " Apple < Banana : "<< (s1 < s2) << endl;
 cout << " Apple > apple : " << (s1 > s4) << endl;
 cout << " Apple <= Banana : " << (s1 <= s2) << endl;
 cout << " Apple == Apple : " << (s1 == "Apple") << endl;
 // Extract a substring from a string
 cout << "--------substring--------" << endl;
 cout << sentence.substr(1, 6) << endl;
 // Find a substring in a string
 cout << "--------find--------" << endl;
 cout << sentence.find("powerful") << endl; // search throuch entire string
 cout << sentence.find("a",2) << endl; // start searching from 2 index
 cout << sentence.find("XX") << endl; // It returns string::npos
 cout << "It start searching from right to left :  " <<sentence.rfind("+")<< endl;
 cout << "It start searching from left to right : " << sentence.find("+")<<endl;
 // find substring in a string game
 cout << "--------find_first_of--------" << endl;
 string word {};
 cout << "\nEnter the word to find from sentence : ";
 cin >> word;
 size_t position = s1.find(word);
 if (position != string::npos) {
 cout << "The word " << word << " is found at position " << position << endl;
 } else {
 cout << "The word " << word << " is not found in the sentence" << endl;
 }
 // Removing characters from a string
 cout << sentence.erase(1, 6) << endl; // erase from index 1 to index 6
 cout << sentence.erase(sentence.find("powerful"), 8) << endl; // erase from index 1 to index 6
 cout << sentence;
 sentence.clear(); // clear the string
 cout << "-------------------------------------" << endl;
 cout << sentence.find("powerful") << endl; // As the string is empty it returns string::npos
 // Inserting characters into a string
 cout << "--------insert--------" << endl;
 string s6 { };
 string s7 { "World" };
 s6.insert(0, "Hello ");
 s6.insert(0, "C++");
 s6.insert(8, "World@@@", 0, 5); // str1.insert(pos,str2); 
 cout << s6<< endl;
 // Replacing characters in a string
 cout << "--------replace--------" << endl;
 string s8 { "Hello World" };
 s8.replace(0, 5, "C++");
 cout << s8 << endl;
 // String length
 cout << "--------length--------" << endl;
 cout << s8.length() << endl;
 // getline function, As insetion operator trim the string where it found the whitespace
 cout << "--------getline--------" << endl;
 string s9 {};
 getline(cin, s9, 'x'); // getline( istream& is, string& str, char delim );  // default delimiter is null character
 return 0;
}
```


>[!Output]
>-- concatenation --
>C++ is a powerful language!!!!!!!
>C
>+
>After assigning 'Q' at 0th and '-' at 1 : Q-+ is a powerful language!!!!!!!
>
>--------looping--------
>C
>+
>+
>
>--------range based for loop--------
>C
>+
>+
>67
>43
>43
> s1 == s2 : false
> Apple == Apple  : true
> Apple == apple : false
> Apple != Kiwi : true
> Apple < Banana : true
> Apple > apple : false
> Apple <= Banana : true
> Apple == Apple : true
>--------substring--------
>-+ is
>--------find--------
>9
>7
>4294967295
>It start searching from right to left : 2
>It start searching from left to right : 2
>--------find_first_of--------
>
>Enter the word to find from sentence : pow
>The word pow is not found in the sentence
>Qa powerful language!!!!!!!
>Qa  language!!!!!!!
>Qa  language!!!!!!!-------------------------------------
>4294967295
>--------insert--------
>C++HelloWorld
>--------replace--------
>C++ World
>--------length--------
>9
>--------getline--------
>ran 
>like
>trex




## Section Challenge 

```cpp
[[include]] <iostream>
[[include]] <string>

using namespace std;
int main() {
	string s {};
    char c {};
    char d {};
    cout << "To Encrypt or Decrypt? (e/d): ";
    cin >> d;
    /* This may be due to a '\n' left in the stream from some other part of your program. 
    Flush the stream before using getline().
    Try using cin.ignore() or cin.sync and cin.clear ,your problem will be solved. */

    cin.sync();

    if ( d ==  'e' || d == 'E') {
        getline(cin, s);
        for (int i {0}; i < s.length(); ++i) {
            c = s[i];
            c = c + 126;
            cout << c ;
    }
    }
    else if ( d == 'd' || d == 'D') {
        getline(cin, s);
        for (int i {0}; i < s.length(); ++i) {
            c = s[i];
            c = c - 126;
            cout << c ;
    }
    }
    else {
        cout << "Invalid Input" << endl;
    }
return 0;
}
```
> [!Output]
> To Encrypt or Decrypt? (e/d): d
> Θ▀≡▀∞₧±τ∞σµ₧»░▒▓│┤
> karan singh 123456

```cpp
[[include]] <iostream>
[[include]] <string>

using namespace std;
int main() {
	string alphabets {"abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ }{1234567890"};
    string keys {"8iEop6aYsRdfgOPqA u7{1h9jklz5}SwDF0GHJxcvb4KLeZXCVUI2BNrMtnTmQW3y"};
    string secret_message {};
    cout << "Enter the secret message: ";
    getline(cin, secret_message);
    string encrypted_message {};
    cout <<"\n Encrypting the message..." << endl;

    for (char c : secret_message) {
        size_t pos = alphabets.find(c);
        if (pos != string::npos) {  // we found the character
            char new_char = keys[pos];
            encrypted_message += new_char;
        } else {
            encrypted_message += c;
        }
    }
    cout << "Encrypted message: " << encrypted_message << endl;

    string decrypted_message {};
    cout << "\n Decrypting the message..." << endl;
    for (int i{0} ; encrypted_message.size() > i ; ++i) {
        char c = encrypted_message[i];
        size_t pos = keys.find(c);
        if (pos != string::npos) {  // we found the character
            char new_char {alphabets.at(pos)};
            decrypted_message += new_char;
        } else {
            decrypted_message += c;
        }
    }
    cout << "Decrypted message: " << decrypted_message << endl;
return 0;
}

```

>[!Output]
>Enter the secret message: karan rawat 181323
>
> Encrypting the message...
>Encrypted message: d8 8O2 8h872rWrtMt
>
> Decrypting the message...
>Decrypted message: karan rawat 181323


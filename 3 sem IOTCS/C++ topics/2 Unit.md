| Topic                                        | Topic                                    |
| -------------------------------------------- | ---------------------------------------- |
| 1. [Specifying a class](#1)                  | 13. [string](#13)                        |
| 2. [creating class objects](#2)              | 14. [The standard C++ String class](#14) |
| 3. [accessing class members](#3)             | 15. [length](#15)                        |
| 4. [access specifies and static members](#4) | 16. [capacity](#16)                      |
| 5. [use of const keyword](#5)                | 17. [resize](#17)                        |
| 6. [friends function](#6)                    | 18. [capacity](#18)                      |
| 7. [empty classes](#7)                       | 19. [get](#19)                           |
| 8. [nested classes](#8)                      | 20. [line](#20)                          |
| 9. [local classes](#9)                       | 21. [begin](#21)                         |
| 10. [abstract classes](#10)                  | 22. [end](#22)                           |
| 11. [container classes](#11)                 | 23. [copy](#23)                          |
| 12. [bit fields and classes](#12)            | 24. [swap etc](#24)                      |

---

# Classes and Objects:

### 1. Specifying a class<a id="1"></a>

### 2. creating class objects<a id="2"></a>

### 3. accessing class members<a id="3"></a>

### 4. access specifies and static members<a id="4"></a>

### 5. use of const keyword<a id="5"></a>

### 6. friends function<a id="6"></a>

### 7. empty classes<a id="7"></a>

### 8. nested classes<a id="8"></a>

### 9. local classes<a id="9"></a>

### 10. abstract classes<a id="10"></a>

### 11. container classes<a id="11"></a>

### 12. bit fields and classes<a id="12"></a>

<br>

# String: Concept of string

### 13. string<a id="13"></a>

### 14. The standard C++ String class<a id="14"></a>

```c++
// Include the string library
#include <string>

// Create a string variable
string greeting = "Hello";
```

<br>

# Operations on Strings:

### 15. length<a id="15"></a>

How to use length() method, for getting length of string

```c++
#include <iostream>
#include <string>
using namespace std;

int main() {
  string txt = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
  cout << "The length of the txt string is: " << txt.length();
  return 0;
}
```

---

### 16. capacity<a id="16"></a>

### 17. resize<a id="17"></a>

```c++


  string str ("ABCDEFGHIJKLMNOPQRSTUVWXYZ");

  //size of the string is reduced to 6
  str.resize(6);
  cout<<"str contains: "<<str << "\n";

  //size of the string is expanded to 7 with character 'C'
  str.resize(7, 'C');
  cout<<"str contains: "<<str << "\n";

  //size of the string is expanded to 9 with character '+'
  str.resize(11, '+');
  cout<<"str contains: "<<str << "\n";
  return 0;

```

### 18. capacity<a id="18"></a>

### 19. getline<a id="19"></a>

```c++
#include <iostream>
#include <string>
using namespace std;

int main() {
  string str ("ABCDEFGHIJKLMNOPQRSTUVWXYZ");


  string name; // variable declaration.
  cout << "Enter your name :" << endl;
  getline(cin,name); // implementing a getline() function
  cout<<"\nHello "<<name;

  return 0;
}
```

### 20. getline<a id="20"></a>

### 21. begin<a id="21"></a>

### 22. end<a id="22"></a>

### 23. copy<a id="23"></a>

### 24. swap etc<a id="24"></a>

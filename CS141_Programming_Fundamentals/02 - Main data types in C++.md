● [02 - Main data types in C++](https://youtu.be/XOx-Wlfle18?feature=shared)

---
# Initialization:

● You can give variables a value as you declare them by placing an equal sign and a value after the variable name.

● The general form of initialization is:  
            `type variable_name = value;`

● Examples:

   ○ char ch = 'a';
   
   ○ int first = 0;  
   
   ○ float balance = 123.23;

1) Copy Initialization
```cpp
#include <iostream>  
  
using namespace std;  
  
int main() {  
    int x = 5;  
    cout << x << endl;  
    return 0;  
}
```

```bash
5
```

2) Direct Initialization
```cpp
#include <iostream>  
  
using namespace std;  
  
int main() {  
    int x = 5;  
    int y(7);  
    cout << "x = " << x << endl;  
    cout << "y = " << y << endl;  
    return 0;  
}
```

```bash
x = 5
y = 7
```

3) Uniform Initialization
```cpp
#include <iostream>  
  
using namespace std;  
  
int main() {  
    int x{5};  
    int y{7};  
    cout << "x = " << x << endl;  
    cout << "y = " << y << endl;  
    return 0;  
}
```

```bash
x = 5
y = 7
```

## Those who do not feel the loss in the data:

1) Copy Initialization
2) Direct Initialization

```cpp
#include <iostream>  
  
using namespace std;  
  
int main() {  
    int x = 6.5;  
    int y(5.4);  
    cout << "x = " << x << endl;  
    cout << "y = " << y << endl;  
    return 0;  
}
```

```Bash
x = 6
y = 5
```

## This is contrary to the third method:

3) Uniform Initialization
```cpp
#include <iostream>  
  
using namespace std;  
  
int main() {  
    int x{6.5};  
    cout << "x = " << x << endl;  
    return 0;  
}
```

```Bash
C:/Users/Joe/CLionProjects/untitled1/main.cpp: In function 'int main()':
C:/Users/Joe/CLionProjects/untitled1/main.cpp:6:11: error: narrowing conversion of '6.5e+0' from 'double' to 'int' [-Wnarrowing]
    6 |     int x{6.5};
      |           ^~~
ninja: build stopped: subcommand failed.
```

---
# Data Types:

## Modifying the Basic Types

● Except for type void, the basic data types may have various modifiers preceding them.  

● You use a modifier to alter the meaning of the base type.

● The list of modifiers is shown here:

   ○ signed  
   ○ unsigned  
   ○ long  
   ○ short

● The difference between signed and unsigned integers is:
  the way that the high order bit of the integer is interpreted. If you specify a signed integer, the compiler generates code that assumes that the high-order bit of an integer is to be used as a sign flag. If the sign flag is 0, the number is positive; if it is 1, the number is negative

● You can apply the modifiers signed, short, long, and unsigned to integer.

● You can apply unsigned and signed to characters.

● You may also apply long to double.

● The use of signed on integers is allowed, but redundant because the default integer declaration assumes a signed number. The most important use of signed is to modify char in implementations in which char is unsigned by default.

| Type               | Size (in bytes)  <br> | Range ==> 2^n  (n is in bits)<br>Unsigned ==>from 0 to 2^n -1<br>Signed ==>from -2^(n-1) to (2^(n-1)) - 1  |
| ------------------ | --------------------- | --------------------------------------------------------------------------------------------------------- |
| bool               | 1                     | false or tr                                                                                                |
| short int          | 2                     | -32,768 to 32,                                                                                             |
| int                | 4                     | -2,147,483,648 to 2,147,483                                                                                |
| long int           | 4                     | -2,147,483,648 to 2,147,48                                                                                 |
| long long          | 8                     | -9,223,372,036,854,775,808 to 9,223,372,036,854,7                                                          |
| char               | 1                     | -128 to 127 \|\| 0                                                                                         |
| float              | 4                     | +/-3.4e+/-38 (~7                                                                                           |
| double             | 8                     | +/-1.7e+/-308 t (~1                                                                                        |
| long double        | 16                    | +/-1.1e+/-4932 (~18–                                                                                       |
| unsigned char      | 1                     | 0 to 255                                                                                                   |
| unsigned int       | 4                     | 0 to 4                                                                                                     |
| unsigned long long | 8                     | 0 to 18,446,744,07                                                                                         |
| string             | ∞                                                                                                                                  |

```cpp
#include <iostream>  
#include <string>  
#include <limits>  
using namespace std;  
  
int main() {  
    bool bl = true;  
    short int si = 32000;  
    int i = 2147483647;  
    long int li = 2147483647;  
    long long ll = 9223372036854775807;  
    char ch = 'A';  
    float f = 3.1415927f;  
    double d = 3.141592653589793;  
    long double ld = 3.141592653589793238L;  
    unsigned char uc = 255;  
    unsigned int ui = 4294967295;  
    unsigned long long ull = 18446744073709551615ULL;  
    string s = "Hello, world!";  
  
    cout << "bool: " << bl << " | size: " << sizeof(bl) << " bytes\n";  
    cout << "short int: " << si << " | size: " << sizeof(si) << " bytes\n";  
    cout << "int: " << i << " | size: " << sizeof(i) << " bytes\n";  
    cout << "long int: " << li << " | size: " << sizeof(li) << " bytes\n";  
    cout << "long long: " << ll << " | size: " << sizeof(ll) << " bytes\n";  
    cout << "char: " << ch << " (" << (int)ch << ") | size: " << sizeof(ch) << " bytes\n";  
    cout << "float: " << f << " | size: " << sizeof(f) << " bytes\n";  
    cout << "double: " << d << " | size: " << sizeof(d) << " bytes\n";  
    cout << "long double: " << ld << " | size: " << sizeof(ld) << " bytes\n";  
    cout << "unsigned char: " << (int)uc << " | size: " << sizeof(uc) << " bytes\n";  
    cout << "unsigned int: " << ui << " | size: " << sizeof(ui) << " bytes\n";  
    cout << "unsigned long long: " << ull << " | size: " << sizeof(ull) << " bytes\n";  
    cout << "string: " << s << " | size (object only): " << sizeof(s) << " bytes\n";  
  
    return 0;  
}
```

```Bash
bool: 1 | size: 1 bytes
short int: 32000 | size: 2 bytes
int: 2147483647 | size: 4 bytes
long int: 2147483647 | size: 4 bytes
long long: 9223372036854775807 | size: 8 bytes
char: A (65) | size: 1 bytes
float: 3.14159 | size: 4 bytes
double: 3.14159 | size: 8 bytes
long double: 3.14159 | size: 16 bytes
unsigned char: 255 | size: 1 bytes
unsigned int: 4294967295 | size: 4 bytes
unsigned long long: 18446744073709551615 | size: 8 bytes
string: Hello, world! | size (object only): 32 bytes
```

## Overflow

Unsigned: Value % range = the value of overflow
```cpp
#include <iostream>  
  
using namespace std;  
  
int main() {  
    unsigned short x = 65536;  //overflow'll = 65536 % 65535 = 0   
cout << x << endl;  
    return 0;  
}
```

```Bash
0
```

`--------------------------------------`

```cpp
#include <iostream>  
  
using namespace std;  
  
int main() {  
    unsigned short x = 3;  
    x = x - 7; // -4 ==> 65,532  
    cout << x << endl;  
  
    /*  
      0 ==> 65,535     -1 ==> 65,535     -2 ==> 65,534     -3 ==> 65,533     -4 ==> 65,532     */    return 0;  
}
```

```Bash
65,532
```


Signed: Unexpected(Random)

---
# Identifier Names

● In C/C++, the names of variables, functions, labels, and various other user-defined objects are called identifiers.

● The first character must be a letter or an underscore, and subsequent characters must be either letters, digits, or underscores.

| Correct      | Incorrect      |
| ------------ | -------------- |
| Count        | 1count         |
| Test23       | hi!there       |
| high_balance | high...balance |

● In an identifier, upper- and lowercase are treated as distinct. Hence, count, Count, and COUNT are three separate identifiers.

● An identifier cannot be the same as a C or C++ keyword, and should not have the same name as functions that are in the C or C++ library.

## Variables

● variable is a named location in memory that is used to hold a  
value that may be modified by the program.

● All variables must be declared before they can be used.
● The general form of a declaration is:
            `type variable_list;`

● Here are some declarations:

   ○ int i,j,l;  
   ○ short int si;  
   ○ unsigned int ui;

## Const variables
● Variables of type const may not be changed by your program. (A const variable can be given an initial value, however.)
                `const int a=10;`

---
# Cast

● You can force an expression to be of a specific type by using a cast. The general form of a cast is:

## Before casting:
```cpp
#include <iostream>  
  
using namespace std;  
 int main() {  
    int x = 5;  
     cout << x / 2 << endl;  
return 0;  
}
```

```Bash
2
```

## After Casting:
```cpp
#include <iostream>  
  
using namespace std;  
 int main() {  
    int x = 5;  
     cout << (float)x / 2 << endl;  
return 0;  
}
```

```Bash
2.5
```

## eg.
```cpp
#include <iostream>  
  
using namespace std;  
 int main() {  
    cout << (int)3.4 << endl;  
     cout << (double) (25) / 2 << endl;  
     cout << (double) (25 / 2) << endl;  
     cout << (int) (3.8 + (double(13) / 2)) << endl;  
return 0;  
}
```

```Bash
3
12.5
12
10
```

---
# Operators

● There are four main classes of operators:
   ○ Arithmetic
   ○ Relational
   
   ○ Logical
   
   ○ Bitwise.
   
   ● The general form of the assignment operator is:
            `variable_name = expression;`

 Eg.1
```cpp
#include <iostream>  
  
using namespace std;  
 int main() {  
    int x;  
     x = 5;  
     cout << "X = " << x << endl;  
return 0;  
}
```

```Bash
X = 5
```

 Eg.2
```cpp
#include <iostream>  
  
using namespace std;  
 int main() {  
    int x, y, z;  
     y = z = 5; // Multible Assignments  
     x = y + z;  
     cout << "X = " << x << endl;  
return 0;  
}
```

```Bash
X = 10
```

## Arithmetic Operators

| Operator | Action                        |
| -------- | ----------------------------- |
| -        | Subtraction, also unary minus |
| +        | Addition                      |
| *        | Multiplication                |
| /        | Division                      |
| %        | Modulus                       |
| --       | Decrement                     |
| ++       | Increment                     |

● When you apply / to an integer any remainder will be truncated.   
     For example, 5/2 will equal 2 in integer division.

● The modulus operator yielding the remainder of an integer division.

Eg.1
```cpp
#include <iostream>  
  
using namespace std;  
 int main() {  
    int x, y;  
     x = 5;  
     y = 2;  
     cout << x << " / " << y << " = " << x / y << endl;  
     cout << x << " % " << y << " = " << x % y << endl;  
return 0;  
}
```

```Bash
5 / 2 = 2
5 % 2 = 1
```

Eg.2
```cpp
#include <iostream>  
  
using namespace std;  
 int main() {  
    int i = 5, j = 6, k = 7, n = 3;  
     cout << i + j * k - k % n << endl;  
return 0;  
}
```

```Bash
46
```

Eg.3
```cpp
#include <iostream>  
  
using namespace std;  
 int main() {  
    cout << 3.0 * 7.0 - 6.0 + 2.0 * 5.0 / 4.0 + 6.0 << endl;  
    cout << (5 + 4) * 2 - 6 / 2 << endl;  
    cout << 4 % 3 * 20 / 2 << endl;  
    cout << (8 + 6) / 2 * 3 % 4 + 6 << endl;  
return 0;  
}
```

```Bash
23.5
15
10
7
```

Eg.4
```cpp
#include <iostream>  
  
using namespace std;  
 int main() {  
    cout << "hello" << "world, " << "again!" << endl;  
    cout << "hello" << endl << "one more time" << endl << 5 << 4 << 3<< " " << 2.2 << " " << 1.1 << endl;  
       
return 0;  
}
```

```Bash
helloworld, again!
hello
one more time
543 2.2 1.1

```

Eg.5 : Write a C++   program that ask the user to enter 2 integers and print their sum, difference, product and division, Mod.
```cpp
#include <iostream>  
  
using namespace std;  
 int main() {  
int x, y;  
  cout << "Enter the first number: ";  
     cin >> x;  
     cout << "Enter the second number: ";  
     cin >> y;  
     cout << x << " + " << y << " = " << x + y << endl;  
     cout << x << " - " << y << " = " << x - y << endl;  
     cout << x << " * " << y << " = " << x * y << endl;  
     cout << x << " / " << y << " = " << x / y << endl;  
     cout << x << " % " << y << " = " << x % y << endl;  
return 0;  
}
```

```Bash
Enter the first number:5

Enter the second number:6

5 + 6 = 11
5 - 6 = -1
5 * 6 = 30
5 / 6 = 0
5 % 6 = 5
```

Eg.6 : Write a C++   program that ask the user to enter a number and print its square using function.
```cpp
#include <iostream>  
#include <math.h>  
using namespace std;  
 int main() {  
int x;  
     cout << "Enter a number: ";  
  cin >> x;  
     cout << pow(x,2) << endl;  
return 0;  
}
```

```Bash
Enter a number:5

25
```

---

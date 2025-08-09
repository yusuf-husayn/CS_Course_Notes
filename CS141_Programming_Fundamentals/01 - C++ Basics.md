● [01 - C++ Basics](https://youtu.be/Cj-oEyBP0kw?feature=shared)

---
# Printing
## cin

● cin is defined in `<iostream>` header file.
●  cin is used to accept the input from the user.
● General form to accept single input :
             `cin >> varName;`
● General form to accept multiple  inputs:
    `cin >> var1 >> var2 >> ... >> varN;`


## cout 

● cout is defined in `<iostream>` header file.
●  cout is•used to output something to the user.
● General form to accept single output :
             `cout << varName;`
● General form to accept multiple  outputs:
    `cout << var1 << "Some String" << var2 << endl;`

---
# Comments
● Comments are for the reader, not the compiler

● Two types:
○ Single line
```cpp
// This is a C++ program. It prints the sentence:
    // Welcome to C++ Programming.
```

○ Multiple line
```cpp
/*
 You can include comments that can
  occupy several lines. 
    */
```

---
# Arithmetic Operations

## Read two integer numbers from the user then print their sum and average.
```cpp
#include <iostream>  
  
using namespace std;  
  
int main() {  
int num1, num2;  
    cout << "Enter two numbers" << endl;  
    cin >> num1 >> num2;  
    cout << "sum of 2 numbers = " << num1 + num2 << endl;  
    cout << "average of 2 numbers = " << (num1 + num2) / 2 << endl;  
return 0;  
}
```

```Bash
Enter two numbers
5
6
sum of 2 numbers = 11
average of 2 numbers = 5
```

## Read a positive integer from the user and print its square
```cpp
#include <iostream>  
#include <math.h>  
  
using namespace std;  
  
int main() {  
int num1;  
    cout << "Enter number : " << endl;  
    cin >> num1;  
    cout << "Power = " << num1 * num1 << endl;  
    cout << "Power using Pow function " << pow(num1, 2)<< endl;  
return 0;  
}
```

```Shell
Enter number :
6
Power = 36
Power using Pow function 36
```

---
# Backslash codes
## " \a" 
 
==> This makes a sound while printing.
 
```cpp
#include <iostream>  
  
using namespace std;  
int main() {  
    int x;  
cout << "Enter your value: \a" << endl;   // + Sound
    cin >> x;  
    return 0;  
}
```

```bash
Enter your value: + sound
```

`--------------------------------------`
## " \b"

==> Each \b deletes a letter from the end of the sentence.

```cpp
#include <iostream>  
  
using namespace std;  
int main() {  
    int x;  
cout << "Yusuf Mohammad \b\b\b\b\b\b\b\b\bMuhammad" << endl;
    return 0;  
}
```

```bash
Yusuf Muhammad
```

`--------------------------------------`
## " \n"

==> Each \n drops to a new line.

```cpp
#include <iostream>  
  
using namespace std;  
int main() {  
    int x;  
       cout << "Yusuf \n\n\nMuhammad" << endl;
    return 0;  
}
```

```bash
Yusuf


Muhammad
```

`--------------------------------------`
## " \r"

==> It returns the pointer to the first line where it is.

```cpp
#include <iostream>  
  
using namespace std;  
int main() {  
    int x;  
       cout << "Muhammad\rYusuf" << endl;  
    return 0;  
}
```

```bash
Yusufmad
```

`--------------------------------------`
## "\t"

==> It leaves 8 horizontal displacements.

```cpp
#include <iostream>  
  
using namespace std;  
int main() {  
    int x;  
       cout << "Computer\tScience\tDepartment\t7\t8" << endl;  
    return 0;  
}
```

```bash
Computer        Science Department      7       8
```

`--------------------------------------`
## " \ " "

==> \ " This prints the== =="==

```cpp
#include <iostream>  
  
using namespace std;  
int main() {  
    int x;  
       cout << "Computer\"Department\"" << endl;  
    return 0;  
}
```

```bash
Computer"Department"
```

`--------------------------------------`
## " \ ' "

==> \ ' This prints the =='==

```cpp
#include <iostream>  
  
using namespace std;  
int main() {  
    int x;  
       cout << "Computer\'Department\'" << endl;  
    return 0;  
}
```

```bash
Computer'Department'
```

`--------------------------------------`
## " \ \ "

==> \ \ This prints the ==\ ==

```cpp
#include <iostream>  
  
using namespace std;  
int main() {  
    int x;  
       cout << "Computer\\Department\\" << endl;  
    return 0;  
}
```

```bash
Computer\Department\
```

`--------------------------------------`
## "\ ? "

==> This is to print the question mark, and we can print it normally.

```cpp
#include <iostream>  
  
using namespace std;  
int main() {  
    int x;  
       cout << "Computer\?Department\?" << endl;  
       cout << "Computer?Department?" << endl;  
  
    return 0;  
}
```

```bash
Computer?Department?
Computer?Department?
```

`--------------------------------------`
## "\ + oct num"

==> This will print the character corresponding to the octal number in the Dec system.

```cpp
#include <iostream>  
  
using namespace std;  
int main() {  
    int x;  
       cout << "\101"<< endl;  
    return 0;  
}
```

```bash
A
```

`--------------------------------------`
## " \ x + Hex num "

==> This will print the character corresponding to the number 16 in the decimal system.

```cpp
#include <iostream>  
  
using namespace std;  
int main() {  
    int x;  
       cout << "\x41"<< endl;  
    return 0;  
}
```

```bash
A
```

| Code          | Meaning                         |
| ------------- | ------------------------------- |
| \a            | Alert (bell)                    |
| \b            | Backspace                       |
| \n            | New line                        |
| \r            | Carriage return                 |
| \t            | Horizontal tab                  |
| \ "           | Double quotes                   |
| \ '           | Single qoute                    |
| \ \           | Backslash                       |
| \ ?           | Question mark                   |
| \ + oct num   | Character with given octal code |
| \ x + Hex num | Character with given hex code   |
| \0            | Null character (NUL)            |

<img width="1692" height="1123" alt="Image" src="https://github.com/user-attachments/assets/71c9caa2-96da-4787-9be4-6d471459c301" />

---
## Function(Structure)

==> This is a part of the code that does a specific task, and every time I call it anywhere in the code, it performs the same function.

```cpp
#include <iostream>  
  
using namespace std;  
void f(int x)  
{  
    int y = x * x - 7 * x + 11;  
    cout << "f( " << x << ") = " << y << endl;  
}  
int main() {  
    f(1);  
    f(2);  
    f(3);  
    f(0);  
    return 0;  
}
```

```bash
f( 1) = 5
f( 2) = 1
f( 3) = -1
f( 0) = 11
```

`--------------------------------------`

```cpp
#include <iostream>  
  
using namespace std;  
int sum(int a, int b) {  
    int z = a +b;  
    cout << "sum of " << a << " and " << b << " = " << z << endl;  
    return 0;  
} int main() {  
    sum(3, 4);  
    sum(5, 6);  
    int x,y;  
    cout << "enter 2 numbers: " << endl;  
    cin >> x >> y;  
    sum(x, y);  
return 0;  
}
```

```Bash
sum of 3 and 4 = 7
sum of 5 and 6 = 11
enter 2 numbers:
6
7
sum of 6 and 7 = 13
```

---

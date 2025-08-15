● [03 - C++ Float and Double](https://www.youtube.com/watch?v=LF778_XjAj8&list=PLp2eAGIFKMEWePxaDmEYE5yS6a9JQMbNs&index=3)

---

# Solving Quadrant Equation

1) With Double

```cpp
#include <iostream>  
#include <math.h>  
using namespace std;  
 int main() {  
double a, b, c;  
     cout << "*************************" << endl;  
     cout << "Solving Quadrant Equation" << endl;  
     cout << "a*x*x + b*x + c" << endl;  
     cout << "*************************" << endl;  
     cout << "Enter a: " << endl;  
     cin >> a;  
     cout << "Enter b: " << endl;  
     cin >> b;  
     cout << "Enter c: " << endl;  
     cin >> c;  
     double x = (-1 * b - sqrt(b * b - 4 * a * c)) / 2 * a;  
     cout << "X1 = " << x << endl;  
      x = (-1 * b + sqrt(b * b - 4 * a * c)) / 2 * a;  
      cout << "X2 = " << x << endl;  
return 0;  
}
```

```Bash
*************************
Solving Quadrant Equation
a*x*x + b*x + c
*************************
Enter a:
1 

Enter b:
4

Enter c:
-21

X1 = -7
X2 = 3
```


2) With Float

```cpp
#include <iostream>  
#include <math.h>  
using namespace std;  
 int main() {  
float a, b, c;  
     cout << "*************************" << endl;  
     cout << "Solving Quadrant Equation" << endl;  
     cout << "a*x*x + b*x + c" << endl;  
     cout << "*************************" << endl;  
     cout << "Enter a: " << endl;  
     cin >> a;  
     cout << "Enter b: " << endl;  
     cin >> b;  
     cout << "Enter c: " << endl;  
     cin >> c;  
     float x = (-1 * b - sqrt(b * b - 4 * a * c)) / 2 * a;  
     cout << "X1 = " << x << endl;  
      x = (-1 * b + sqrt(b * b - 4 * a * c)) / 2 * a;  
      cout << "X2 = " << x << endl;  
return 0;  
}
```

```Bash
*************************
Solving Quadrant Equation
a*x*x + b*x + c
*************************
Enter a:
1 

Enter b:
4

Enter c:
-21

X1 = -7
X2 = 3
```

---
# How does the computer represent the Double and the float

## ● IEEE 754 Representation

### ○ Float 32 bit
```
1bit               ←8 bit→                         ←23 bits→
■                  ■■■■■■■■                  ■■■■■■■■■■■■■■■■■■■■■■■
⬆sign             ⬆exponent                ⬆mantissa
```
```
### ○ Double 64 bit

1bit               ←11 bit→                        ←52 bits→
■                  ■■■■■■■■                  ■■■■■■■■■■■■■■■■■■■■■■■
⬆sign             ⬆exponent                ⬆mantissa
```

   ○ Eg. ==> 85.125

85 ==> 01010101
.125 ==> 001

85.125 ==> 1010101.001 ==> 1.010101001 x 2^6

 ○ Float 32 bit
```
1bit               ←8 bit→                         ←23 bits→
■                  ■■■■■■■■                  ■■■■■■■■■■■■■■■■■■■■■■■
0                  6 + 127 = 133                     010101001
0                  10000101                  01010100100000000000000
```

```cpp
#include <iostream>  
#include <math.h>  
using namespace std;  
 int main() {  
double a;  
  float f;  
cout << "Float : " << sizeof(f) << " Bytes " << endl;  
cout << "Double : " << sizeof(a) << " Bytes " << endl;  
cout << "Long Double : " << sizeof(long double) << " Bytes " << endl;  
  
return 0;  
}
```

```Bash
Float : 4 Bytes
Double : 8 Bytes
Long Double : 16 Bytes
```


---
# Unions
In C++, a union is a user-defined data types that allow you to store different types of data in the same memory location but unlike structures, where each member gets its own memory, union members share the same memory space making unions more memory-efficient for specific use cases.

```cpp
#include <iostream>  
using namespace std;  
 int main() {  
union {  
 int x;  
 long z;  
} data;  
     data.x = 7;  
     cout << data.x << endl;  
     cout << data.z << endl;  
return 0;  
}
```

```Bash
7
7
```

```cpp
#include <iostream>  
using namespace std;  
 int main() {  
union {  
 float x;  
 int z;  
} data;  
     data.x = 85.125;  
     cout << hex << data.z << endl;  
     // 42aa4000 = 0 10000101 01010100100000000000000  
return 0;  
}
```

```Bash
42aa4000
```

---
# Increment and Decrement

● The operator ++ adds 1 to its operand, and - - subtracts 1.

● Both the increment and decrement operators may either prefix or postfix the operand.

                      x=x+1   x++  or ++x

                      x=x-1    x-- or --x

● When an increment or decrement operator precedes its operand, the increment or decrement operation is performed before obtaining the value of the operand for use in the expression. If the operator follows its operand, the value of the operand is obtained before incrementing or decrementing it

| x = 10;<br>y = ++x; | x = 10;<br>y = x ++ | x = 10;<br>y = --x | x = 10;<br>y = x-- |
| ------------------- | ------------------- | ------------------ | ------------------ |
| Sets y to 11        | Sets y to 10        | Set y to 9         | Set y to 10;       |

● The precedence of the arithmetic operators:

| Operators (ordered)        | Associativity | Degree  |
| -------------------------- | ------------- | ------- |
| ++, -- (postfix)           | left to right | Highest |
| ++, -- (prefix), - (unary) | right to left |         |
| * / %                      | left to right |         |
| + -                        | left to right |         |
| < <= > >=                  | left to right |         |
| == !=                      | left to right |         |
| &&                         | left to right |         |
| \|\|                       | left to right |         |
| = += -= *= /= %=           | right to left | Lowest  |

Eg.1
```cpp
#include <iostream>  
using namespace std;  
 int main() {  
int x = 5;  
  int y = 10;  
     int z = ++x * y-- + 10;  
     cout << " z = " << z << endl;  
     cout << " x = " << x << endl;  
     cout << " y = " << y << endl;  
return 0;  
}
```

```Bash
 z = 70
 x = 6
 y = 9
```

Eg.2
```cpp
#include <iostream>  
using namespace std;  
 int main() {  
int x = 5;  
  int y = 10;  
     int z = ++x * --y + 10;  
     cout << " z = " << z << endl;  
     cout << " x = " << x << endl;  
     cout << " y = " << y << endl;  
return 0;  
}
```

```Bash
 z = 64
 x = 6
 y = 9
```


Eg.3 
```cpp
#include <iostream>  
using namespace std;  
 int main() {  
int x = 4;  
  int y = 3;  
    cout << y++ * x-- << endl;  
     cout << ++y * x-- << endl;  
     cout << ++y * --x << endl;  
return 0;  
}
```

```Bash
12
15
6
```

Eg.4
```cpp
#include <iostream>  
using namespace std;  
 int main() {  
int x = 30;  
  int y = 40;  
     int z = ++x * --y + x++ - y -- * 10;  
     cout << " z = " << z << endl;  
     cout << " x = " << x << endl;  
     cout << " y = " << y << endl;  
return 0;  
}
```

```Bash
z = 850
 x = 32
 y = 38
```

---

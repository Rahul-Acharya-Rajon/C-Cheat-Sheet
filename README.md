# C-Cheat-Sheet
# Introduction
C is a low level programming langugae that is created by Denis Ritchie

# First Program
Here is the first line of code
```c
#include <stdio.h>

int main(){
    printf("Hello, World!");
    return 0;
}
```

## Explaination
`#include <stdio.h>` line imports **standard** header file
`int main(){}` declares the **main** function
`printf()` built-in function **prints** text on the output screen


# Data Types
We regularly work with data. There are some basic data types in C:
| Data Type | Description                          | Size (Typical) | Format Specifier | Example             |
|-----------|--------------------------------------|----------------|------------------|---------------------|
| `int`     | Integer number                       | 4 bytes        | `%d` or `%i`      | `int age = 25;`     |
| `float`   | Floating point number (decimal)      | 4 bytes        | `%f`              | `float pi = 3.14;`  |
| `double`  | Double precision float               | 8 bytes        | `%lf`             | `double g = 9.81;`  |
| `char`    | Single character                     | 1 byte         | `%c`              | `char grade = 'A';` |
| `void`    | No value / empty                     | 0 bytes        | —                | `void function()`   |
| `short`   | Short integer                        | 2 bytes        | `%hd`             | `short s = 100;`    |
| `long`    | Long integer                         | 4 or 8 bytes   | `%ld`             | `long l = 100000;`  |
| `long long` | Longer integer                    | 8 bytes        | `%lld`            | `long long big = 1e12;` |
| `_Bool` or `bool` | Boolean (true/false)        | 1 byte         | `%d`              | `bool flag = true;` |


# Variables
A variable can be declared by following the syntax
**data_type** **variable_name** **=** **value** **;**
Actually, the word variable came from **vary** and **able**. So, we can change the value at any time and the **last value will be stayed**.
First declare a variable:

```c
int age;
```

Then initialize the variable
```c
int age = 10;
```

We can do it at the same time
```c
int age = 10;
```

Let's see some example:
```c
int age = 10;
float PI = 3.45;
char star = '*';
```
Rules of creating variables
* Must begin with a letter (A-Z or a-z) or an underscore (_)
* Can be followed by letters, digits (0-9), or underscores
* Cannot start with a digit
* No spaces or special characters (like @, #, $, etc.)
* Case-sensitive: value, Value, and VALUE are different

| Rule                               | Description         | Example |
| ---------------------------------- | ------------------- | ------- |
| ✅ Must begin with letter or `_`    | `int _data;`        | ✅       |
| ❌ Cannot start with number         | `int 1value;`       | ❌       |
| ❌ Cannot use reserved keywords     | `int float;`        | ❌       |
| ✅ Case-sensitive                   | `int var, Var;`     | ✅       |
| ✅ Use `const` for constants        | `const int x = 10;` | ✅       |
| ✅ Use of `bool` with `<stdbool.h>` | `bool flag = true;` | ✅       |

If you assign a new value to an existing variable, it will overwrite the previous value:
```c
int myNum = 15;  // myNum is 15
myNum = 10;  // Now myNum is 10
```

You can also copy a variable like this way
```c
// Create a variable and assign the value 15 to it
int myNum = 15;

// Declare a variable without assigning it a value
int myOtherNum;

// Assign the value of myNum to myOtherNum
myOtherNum = myNum;

// myOtherNum now has 15 as a value
printf("%d", myOtherNum);
```

To declare more than one variable of the same type, use a comma-separated list:
```c
int x = 5, y = 6, z = 50;
printf("%d", x + y + z);
```

You can also assign the same value to multiple variables of the same type:
```c
int x, y, z;
x = y = z = 50;
printf("%d", x + y + z);
```


# Format Specifier
This helps us to use data types in different functions. Each format specifier represents specific data type
| Format Specifier | Represent |
| --- | --- |
| %d | Integer |
| %f | Float |
| %c | Character |

We can use these format specifiers to print different data types
```c
printf("%d", 10);
printf("%f", 239.34);
printf("%.2f", 23.3485344);
printf("%c", 'a');
```

In line 3, we use **.2** to print 2 numbers after decimal point
***Note: Character data type can only be declare within single quotes***
We can print the variables using respective format specifiers
```c
int age = 10;
float PI = 3.1416;
char star = '*';

printf("%d", age);
printf("%f", PI);
printf("%c", star);
```

You can combine string (will be discussed later) with numbers
```c
int myNum = 15;
printf("My favorite number is: %d", myNum);
```

```c
int myNum = 15;
char myLetter = 'D';
printf("My number is %d and my letter is %c", myNum, myLetter);
```


# Escape Sequence Characters
Escape sequence characters are special types of characters that are basically consisting of two characters but work as single character
| Escape Sequence | Character Represented           | Description                            |
| --- | --- | --- |
| `\\`            | Backslash                     | Inserts a backslash (`\`)             |
| `\'`            | Single Quote                  | Inserts a single quote (`'`)          |
| `\"`            | Double Quote                  | Inserts a double quote (`"`)          |
| `\?`            | Question Mark                 | Avoids trigraph issues (`?`)          |
| `\a`            | Alert/Bell                    | Produces an alert or bell sound       |
| `\b`            | Backspace                     | Moves cursor back one space           |
| `\f`            | Formfeed                      | Moves cursor to the beginning of next page |
| `\n`            | Newline                       | Moves cursor to the next line         |
| `\r`            | Carriage Return               | Moves cursor to the beginning of the line |
| `\t`            | Horizontal Tab                | Moves cursor to the next tab stop     |
| `\v`            | Vertical Tab                  | Moves cursor down to next vertical tab stop |
| `\ooo`          | Octal Value                   | Character with octal value `ooo`      |
| `\xhh`          | Hexadecimal Value             | Character with hexadecimal value `hh` |

Here are some examples:
```c
printf("This is a line.\n");            // \n = newline
printf("This is a tab:\tSee?\n");       // \t = tab
printf("This is a backspace: ABC\bD\n"); // \b = backspace
printf("This is a quote: \"Hello\"\n"); // \" = double quote
printf("This is a single quote: \'A\'\n"); // \' = single quote
printf("This is a backslash: \\\n");    // \\ = backslash
printf("This is an alert (bell): \a\n"); // \a = alert (may beep)
printf("This is a question mark: \?\n"); // \? = question mark
printf("Octal: \101\n");                // \101 = 'A' in octal
printf("Hex: \x42\n");                  // \x42 = 'B' in hexadecimal
```
***Note: semicolon (\;) is used to terminate single statement***


# Comments
Comments help us to prevent codes to be executed and to highlight or note in the code. There are **two** types of comments: **single line comment** and **multi line comment**
| Comment Type       | Syntax          | Example                            |
| ------------------ | --------------- | ---------------------------------- |
| Single-line        | `// comment`    | `// This is a single-line comment` |
| Multi-line (block) | `/* comment */` | `/* This is a block comment */`    |

Here is an example 
```c
// This is a single-line comment

/*
 * This is a multi-line comment.
 * It can span several lines.
 */
```


# More On Data Types
## char
The char data type is used to store a single character. The character must be surrounded by single quotes, like 'A' or 'c', and we use the %c format specifier to print it:
```c
char myGrade = 'A';
printf("%c", myGrade);
```

If you try to store more than a single character, it will only print the last character:
```c
char myText = 'Hello';
printf("%c", myText);
```

To store multiple characters (or whole words), use strings
```c
char myText[] = "Hello";
printf("%s", myText);
```

Alternatively, if you are familiar with ASCII, you can use ASCII values to display certain characters. Note that these values are not surrounded by quotes (''), as they are numbers:
```c
char a = 65, b = 66, c = 67;
printf("%c", a);
printf("%c", b);
printf("%c", c);
```

Here is the list of ASCII (**American Standard Code for Information Interchange**):
### ASCII Table (0–127)
| Dec | Char | Dec | Char | Dec | Char | Dec | Char |
|-----|------|-----|------|-----|------|-----|------|
|  0  | NUL  |  1  | SOH  |  2  | STX  |  3  | ETX  |
|  4  | EOT  |  5  | ENQ  |  6  | ACK  |  7  | BEL  |
|  8  | BS   |  9  | TAB  | 10  | LF   | 11  | VT   |
| 12  | FF   | 13  | CR   | 14  | SO   | 15  | SI   |
| 16  | DLE  | 17  | DC1  | 18  | DC2  | 19  | DC3  |
| 20  | DC4  | 21  | NAK  | 22  | SYN  | 23  | ETB  |
| 24  | CAN  | 25  | EM   | 26  | SUB  | 27  | ESC  |
| 28  | FS   | 29  | GS   | 30  | RS   | 31  | US   |
| 32  | (space) | 33  | !    | 34  | "    | 35  | #    |
| 36  | $    | 37  | %    | 38  | &    | 39  | '    |
| 40  | (    | 41  | )    | 42  | *    | 43  | +    |
| 44  | ,    | 45  | -    | 46  | .    | 47  | /    |
| 48  | 0    | 49  | 1    | 50  | 2    | 51  | 3    |
| 52  | 4    | 53  | 5    | 54  | 6    | 55  | 7    |
| 56  | 8    | 57  | 9    | 58  | :    | 59  | ;    |
| 60  | <    | 61  | =    | 62  | >    | 63  | ?    |
| 64  | @    | 65  | A    | 66  | B    | 67  | C    |
| 68  | D    | 69  | E    | 70  | F    | 71  | G    |
| 72  | H    | 73  | I    | 74  | J    | 75  | K    |
| 76  | L    | 77  | M    | 78  | N    | 79  | O    |
| 80  | P    | 81  | Q    | 82  | R    | 83  | S    |
| 84  | T    | 85  | U    | 86  | V    | 87  | W    |
| 88  | X    | 89  | Y    | 90  | Z    | 91  | [    |
| 92  | \\   | 93  | ]    | 94  | ^    | 95  | _    |
| 96  | `    | 97  | a    | 98  | b    | 99  | c    |
|100  | d    |101  | e    |102  | f    |103  | g    |
|104  | h    |105  | i    |106  | j    |107  | k    |
|108  | l    |109  | m    |110  | n    |111  | o    |
|112  | p    |113  | q    |114  | r    |115  | s    |
|116  | t    |117  | u    |118  | v    |119  | w    |
|120  | x    |121  | y    |122  | z    |123  | {    |
|124  | \|   |125  | }    |126  | ~    |127  | DEL  |

## int
Use int when you need to store a whole number without decimals
```c
int myNum = 1000;
printf("%d", myNum);
```

## float & double
The precision of a floating point value indicates how many digits the value can have after the decimal point. The precision of **float** is **six** or **seven** decimal digits, while **double** variables have a precision of about **15 digits**. Therefore, it is often **safer to use double for most calculations** - but note that it takes up twice as much memory as float (**8 bytes vs. 4 bytes**).
```c
float myNum = 5.75;
printf("%f", myNum);
```

```c
double myNum = 19.99;
printf("%lf", myNum);
```

Memory Size
| Data Type | Description            | Typical Size (in bytes) | Format Specifier |
|-----------|------------------------|--------------------------|------------------|
| `char`    | Character               | 1 byte                   | `%c`             |
| `int`     | Integer                 | 4 bytes                  | `%d` or `%i`     |
| `float`   | Single precision float  | 4 bytes                  | `%f`             |
| `double`  | Double precision float  | 8 bytes                  | `%lf`            |

Get the size:
```c
printf("Size of char: %lu bytes\n", sizeof(char));
printf("Size of int: %lu bytes\n", sizeof(int));
printf("Size of float: %lu bytes\n", sizeof(float));
printf("Size of double: %lu bytes\n", sizeof(double));
```

## Scientific Numbers
In C, you can write very large or very small floating-point numbers using scientific notation
```c
float f1 = 35e3;   // 35 * 10^3 = 35000
double d1 = 12E4;  // 12 * 10^4 = 120000

printf("%f\n", f1);
printf("%lf", d1);
```


# Type Conversion
There are two types of conversion in C:
1. Implicit Conversion (automatically)
2. Explicit Conversion (manually)

## Implicit Conversion (automatically)
Implicit conversion is done automatically by the compiler when you assign a value of one type to another
```c
// Automatic conversion: int to float
float myFloat = 9;

printf("%f", myFloat); // 9.000000
```

```c
// Automatic conversion: float to int
int myInt = 9.99;

printf("%d", myInt); // 
```

```c
float sum = 5 / 2;

printf("%f", sum); // 2.000000
```

## Explicit Conversion
Explicit conversion is done manually by placing the type in parentheses () in front of the value
```c
// Manual conversion: int to float
float sum = (float) 5 / 2;

printf("%f", sum); // 2.500000
```
You can also place the type in front of a variable
```c
int num1 = 5;
int num2 = 2;
float sum = (float) num1 / num2;

printf("%f", sum); // 2.500000
```

# Constants
If you don't want others (or yourself) to change existing variable values, you can use the **const** keyword
```c
const int myNum = 15;  // myNum will always be 15
myNum = 10;  // error: assignment of read-only variable 'myNum'
```
Another thing about constant variables, is that it is considered good practice to declare them with uppercase. It is not required, but useful for code readability and common for C programmers:
```c
const int BIRTHYEAR = 1980;
```


# Operators
Using operators, different types of mathematical and logical operations can be performed. Let's see examples:

## 1. Arithmetic Operators

| Operator | Description      | Example     |
|----------|------------------|-------------|
| `+`      | Addition          | `a + b`     |
| `-`      | Subtraction       | `a - b`     |
| `*`      | Multiplication    | `a * b`     |
| `/`      | Division          | `a / b`     |
| `%`      | Modulus           | `a % b`     |

```c
int a = 10, b = 3, result;

// 1. Arithmetic Operators
result = a + b;     // Addition
result = a - b;     // Subtraction
result = a * b;     // Multiplication
result = a / b;     // Division
result = a % b;     // Modulus
```

## 2. Assignment Operators

| Operator | Description                | Example      |
|----------|----------------------------|--------------|
| `=`      | Assign                     | `a = b`      |
| `+=`     | Add and assign             | `a += b`     |
| `-=`     | Subtract and assign        | `a -= b`     |
| `*=`     | Multiply and assign        | `a *= b`     |
| `/=`     | Divide and assign          | `a /= b`     |
| `%=`     | Modulus and assign         | `a %= b`     |

```c
int result = 10;

// 2. Assignment Operators
result = 5;
result += 2;        // result = result + 2
result -= 1;        // result = result - 1
result *= 3;        // result = result * 3
result /= 2;        // result = result / 2
result %= 3;        // result = result % 3
```

## 3. Relational (Comparison) Operators

| Operator | Description          | Example     |
|----------|----------------------|-------------|
| `==`     | Equal to             | `a == b`    |
| `!=`     | Not equal to         | `a != b`    |
| `>`      | Greater than         | `a > b`     |
| `<`      | Less than            | `a < b`     |
| `>=`     | Greater than or equal| `a >= b`    |
| `<=`     | Less than or equal   | `a <= b`    |

```c
int a = 10, b = 3;

// 3. Relational (Comparison) Operators
if (a == b) {}
if (a != b) {}
if (a > b) {}
if (a < b) {}
if (a >= b) {}
if (a <= b) {}
```

## 4. Logical Operators

| Operator | Description        | Example        |
|----------|--------------------|----------------|
| `&&`     | Logical AND         | `a && b`       |
| `||`     | Logical OR          | `a || b`       |
| `!`      | Logical NOT         | `!a`           |

```c
int x = 1, y = 0;

// 4. Logical Operators
if (x && y) {}      // Logical AND
if (x || y) {}      // Logical OR
if (!x) {}          // Logical NOT
```

## 5. Bitwise Operators

| Operator | Description         | Example     |
|----------|---------------------|-------------|
| `&`      | Bitwise AND         | `a & b`     |
| `|`      | Bitwise OR          | `a | b`     |
| `^`      | Bitwise XOR         | `a ^ b`     |
| `~`      | Bitwise NOT         | `~a`        |
| `<<`     | Left shift          | `a << 2`    |
| `>>`     | Right shift         | `a >> 2`    |

```c
int a = 10, b = 3, result;

// 5. Bitwise Operators
result = a & b;     // Bitwise AND
result = a | b;     // Bitwise OR
result = a ^ b;     // Bitwise XOR
result = ~a;        // Bitwise NOT
result = a << 1;    // Left Shift
result = a >> 1;    // Right Shift
```

## 6. Unary Operators

| Operator | Description         | Example     |
|----------|---------------------|-------------|
| `+`      | Unary plus          | `+a`        |
| `-`      | Unary minus         | `-a`        |
| `++`     | Increment           | `a++` or `++a` |
| `--`     | Decrement           | `a--` or `--a` |
| `!`      | Logical NOT         | `!a`        |
| `~`      | Bitwise NOT         | `~a`        |

```c
int a = 10, b = 3, result;

// 6. Unary Operators
result = +a;
result = -b;
a++;                // Post-increment
++a;                // Pre-increment
b--;                // Post-decrement
--b;                // Pre-decrement
result = !x;
result = ~b;
```

## 7. Ternary Operator

| Operator    | Description         | Example             |
|-------------|---------------------|---------------------|
| `? :`       | Ternary (if-else)   | `a ? b : c`         |

```c
int a = 10, b = 3, result;

// 7. Ternary Operator
result = (a > b) ? a : b;
```

## 8. Comma Operator

| Operator | Description         | Example          |
|----------|---------------------|------------------|
| `,`      | Comma separator     | `a = (x = 1, x + 1)` |

```c
int x;

// 8. Comma Operator
result = (x = 5, x + 2);  // x is 5, result is 7
```

## 9. Sizeof Operator

| Operator  | Description         | Example        |
|-----------|---------------------|----------------|
| `sizeof`  | Size in bytes       | `sizeof(int)`  |

```c
// 9. sizeof Operator
printf("Size of int: %lu\n", sizeof(int));
printf("Size of float: %lu\n", sizeof(float));
```

## 10. Pointer and Address Operators

| Operator | Description           | Example     |
|----------|-----------------------|-------------|
| `&`      | Address-of            | `&a`        |
| `*`      | Pointer dereference   | `*ptr`      |

```c
int arr[] = {1, 2, 3};
int *ptr = arr;

// 10. Pointer and Address Operators
printf("Address of a: %p\n", (void*)&a);  // Address-of
printf("Value at ptr: %d\n", *ptr);       // Dereference
```

## 11. Member Access Operators

| Operator | Description            | Example        |
|----------|------------------------|----------------|
| `.`      | Access struct member   | `s.x`          |
| `->`     | Access via pointer     | `ptr->x`       |

```c
// 11. Member Access Operators
struct Point { int x, y; } p = {2, 3};
struct Point *p_ptr = &p;
result = p.x;          // Access member
result = p_ptr->y;     // Access via pointer
```

## 12. Type Casting Operator

| Operator     | Description       | Example          |
|--------------|-------------------|------------------|
| `(type)`     | Type cast         | `(int) 3.14`     |

```c
int a = 10, b = 3;
float f;

// 12. Type Casting Operator
f = (float)a / b;     // Convert to float before division
```


# Booleans
C has a **bool** data type, which is known as **boolean**s. Booleans represent one of two values: **true** or **false**. In C, the bool type is not a built-in data type, like int or char. It was introduced in **C99**, and you must import the following header file to use it:

```c
#include <stdbool.h>
```

A boolean variable is declared with the bool keyword and can take the values true or false

```c
bool isProgrammingFun = true;
bool isFishTasty = false;
```

* 1 (or any other number that is not 0) represents true
* 0 represents false

Therefore, you must use the %d format specifier to print a boolean value

```c
// Create boolean variables
bool isProgrammingFun = true;
bool isFishTasty = false;

// Return boolean values
printf("%d", isProgrammingFun);   // Returns 1 (true)
printf("%d", isFishTasty);        // Returns 0 (false)
```

---
title: C programming language basics
author: AIT EL HAJ Abdelouadoud
description: "C programming is very simple!"
image:
    url: "https://www.svgrepo.com/svg/535245/c"
    alt: "C programming language logo."
pubDate: 2025-03-25
tags: ["C", "C programming language", "Programming", "Coding"]
---

After a successful first week learning Astro, I decided to try some more. I wrote and imported a small component from memory!# C Programming Basics: A Beginner's Guide

C is a powerful, low-level programming language widely used in system programming, embedded systems, and application development. Understanding its basics is essential for anyone learning programming.

## Why Learn C?
- **Efficiency**: C provides fine control over memory and system resources.
- **Portability**: Code written in C can run on various platforms with minimal changes.
- **Foundation for Other Languages**: C influences languages like C++, Java, and Python.

## Writing a Simple C Program
A C program consists of functions, variables, and statements.

### Hello, World!
```c
#include <stdio.h>

int main() {
    printf("Hello, World!\n");
    return 0;
}
```
### Explanation:
- `#include <stdio.h>`: Includes the standard I/O library.
- `int main()`: Main function where execution begins.
- `printf()`: Prints output to the console.
- `return 0;`: Indicates successful execution.

## Variables and Data Types
C has several data types for storing values:

```c
int age = 25;
float pi = 3.14;
char grade = 'A';
```
### Common Data Types:
- `int` - Integer numbers (e.g., 10, -5)
- `float` - Decimal numbers (e.g., 3.14, -2.5)
- `char` - Single characters (e.g., 'A', 'Z')
- `double` - Higher precision floating-point numbers

## Input and Output
### Taking User Input:
```c
#include <stdio.h>

int main() {
    int age;
    printf("Enter your age: ");
    scanf("%d", &age);
    printf("You are %d years old.\n", age);
    return 0;
}
```
### Explanation:
- `scanf()` reads user input.
- `&age` stores the input value in the variable.

## Control Statements
### If-Else Condition:
```c
if (age >= 18) {
    printf("You are an adult.\n");
} else {
    printf("You are a minor.\n");
}
```
### Loops:
```c
// For loop
for (int i = 0; i < 5; i++) {
    printf("Iteration %d\n", i);
}

// While loop
int count = 0;
while (count < 3) {
    printf("Count: %d\n", count);
    count++;
}
```

## Functions in C
Functions help organize code and avoid repetition.

```c
#include <stdio.h>

void greet() {
    printf("Hello from function!\n");
}

int main() {
    greet();
    return 0;
}
```
### Explanation:
- `void greet()` is a user-defined function.
- `greet();` calls the function.

## Arrays and Pointers
### Arrays:
```c
int numbers[5] = {1, 2, 3, 4, 5};
printf("First element: %d\n", numbers[0]);
```
### Pointers:
```c
int a = 10;
int *p = &a;
printf("Value: %d, Address: %p\n", *p, p);
```

## Conclusion
C programming is an essential language for system-level programming. Mastering its basics sets a strong foundation for advanced topics like memory management, data structures, and algorithms.


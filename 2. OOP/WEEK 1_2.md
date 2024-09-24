# WEEK 1_1: Conditional Statements and Loops in Java

### Overview
In this handout, we will explore conditional statements and loops, two foundational concepts in Java programming. These control structures help in making decisions (using conditionals) and performing repetitive tasks (using loops). By the end of this handout, you’ll understand how these structures work in Java, including `if-else` statements, `switch` cases, and the various types of loops (`for`, `while`, and `do-while` loops).

---

## 1. Conditional Statements in Java

### What Are Conditional Statements?
Conditional statements allow the program to make decisions and execute different blocks of code based on certain conditions.

---

### 1.1 **if-else Statements**
The `if-else` statement is used to execute a block of code if a specific condition is true. If the condition is false, the program can optionally execute an `else` block.

#### Syntax
```java
if (condition) {
    // Code to execute if condition is true
} else {
    // Code to execute if condition is false
}
```

#### Example
```java
int number = 5;
if (number > 0) {
    System.out.println("Positive number");
} else {
    System.out.println("Non-positive number");
}
```
- **Condition**: A boolean expression (e.g., `number > 0`).
- If the condition evaluates to `true`, the code inside the `if` block is executed.
- If the condition is `false`, the code inside the `else` block is executed.

### 1.2 **else if Statements**
The `else if` statement allows multiple conditions to be checked.

#### Syntax
```java
if (condition1) {
    // Code for condition1
} else if (condition2) {
    // Code for condition2
} else {
    // Code if none of the conditions are true
}
```

#### Example
```java
int number = 0;
if (number > 0) {
    System.out.println("Positive number");
} else if (number < 0) {
    System.out.println("Negative number");
} else {
    System.out.println("Zero");
}
```

---

### 1.3 **switch Case Statements**
The `switch` statement allows multiple possible values of a variable to be checked, executing different blocks of code depending on the value.

#### Syntax
```java
switch (expression) {
    case value1:
        // Code for value1
        break;
    case value2:
        // Code for value2
        break;
    default:
        // Code if no case matches
}
```

#### Example
```java
int day = 3;
switch (day) {
    case 1:
        System.out.println("Monday");
        break;
    case 2:
        System.out.println("Tuesday");
        break;
    case 3:
        System.out.println("Wednesday");
        break;
    default:
        System.out.println("Invalid day");
}
```
- The `switch` expression is evaluated, and the matching `case` block is executed.
- **`break`**: Ends the execution of the `switch` case. Without it, the program would continue executing the next case statements.
- **`default`**: Optional block executed if none of the cases match.

---

## 2. Loops in Java

### What Are Loops?
Loops allow a block of code to be executed multiple times until a specific condition is met. Java has three main types of loops: `for`, `while`, and `do-while` loops.

---

### 2.1 **for Loop**
A `for` loop is ideal when you know in advance how many times a block of code needs to be executed.

#### Syntax
```java
for (initialization; condition; update) {
    // Code to execute
}
```

#### Example
```java
for (int i = 1; i <= 5; i++) {
    System.out.println("Count: " + i);
}
```
- **Initialization**: Sets a counter variable (e.g., `int i = 1`).
- **Condition**: The loop continues while this condition is `true` (e.g., `i <= 5`).
- **Update**: Updates the counter variable after each iteration (e.g., `i++`).

---

### 2.2 **while Loop**
A `while` loop executes the block of code repeatedly as long as the condition remains `true`.

#### Syntax
```java
while (condition) {
    // Code to execute
}
```

#### Example
```java
int i = 1;
while (i <= 5) {
    System.out.println("Count: " + i);
    i++;
}
```
- The condition is checked before each iteration. If the condition is `true`, the loop runs; otherwise, it stops.

---

### 2.3 **do-while Loop**
A `do-while` loop is similar to a `while` loop, but it guarantees that the code inside the loop will be executed at least once, even if the condition is `false` initially.

#### Syntax
```java
do {
    // Code to execute
} while (condition);
```

#### Example
```java
int i = 1;
do {
    System.out.println("Count: " + i);
    i++;
} while (i <= 5);
```
- The loop body is executed first, and then the condition is checked. If the condition is `true`, the loop continues.

---

## Practice Questions

1. **Write a program** that takes a number as input and prints whether it is positive, negative, or zero using an `if-else` statement.
   
2. **Create a program** using a `switch` statement that takes an integer (1 to 7) as input and prints the corresponding day of the week (e.g., 1 for Monday, 2 for Tuesday, etc.).

3. **Write a program** that prints all even numbers between 1 and 20 using a `for` loop.

4. **Write a program** that uses a `while` loop to print numbers from 10 to 1 in reverse order.

5. **Write a program** that uses a `do-while` loop to repeatedly ask the user for a number and print it, but stop the loop when the user enters 0.

---

### Summary

- **Conditional Statements**: 
  - `if-else` statements allow decision-making in programs.
  - `switch` statements allow for multiple possible outcomes based on the value of a variable.

- **Loops**: 
  - `for` loops are useful when you know the number of iterations beforehand.
  - `while` loops keep running while a condition is true.
  - `do-while` loops guarantee at least one execution of the loop body.

These concepts are essential for building logic in Java programs and controlling the flow of your applications efficiently.
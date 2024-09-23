# WEEK 1_0: Introduction to Java Programming Basics

## Overview
This handout provides an introduction to the basics of programming in Java, focusing on variable declaration, the use of the `Scanner` class for input, and import statements. We'll build on concepts you might already be familiar with from C programming and show how they translate to Java.

### Key Concepts Covered
- **Programming Basics in Java**: Understanding Java syntax and structure.
- **Variable Declaration**: Defining variables with appropriate data types.
- **Scanner Class**: Taking user input in Java.
- **Import Statements**: Using Java libraries effectively.

---

## Programming Basics in Java

### Understanding Java Syntax and Structure
Java programs are written as a series of classes and methods. The structure of a basic Java program looks like this:

```java
public class Main {
    public static void main(String[] args) {
        // Code goes here
    }
}
```
- **Class**: `public class Main` defines a class named `Main`. In Java, every program needs at least one class with a `main` method.
- **Main Method**: `public static void main(String[] args)` is the entry point for any Java application. It is the first method executed by the JVM when the program starts.

### Java vs. C: Similarities and Differences
- **Similarities**: Both Java and C use similar syntax for basic operations like loops, conditionals, and variable declarations.
- **Differences**: Java is object-oriented, whereas C is procedural. Java has built-in memory management (garbage collection), unlike C, which requires manual memory management.

---

## Declaring Variables in Java

### What is a Variable?
A variable in Java, like in C, is a storage location that holds a value. It has a data type that determines what kind of values it can store.

### Variable Declaration Syntax
```java
dataType variableName = value;
```
- **Data Type**: Specifies the type of value (e.g., `int`, `double`, `String`).
- **Variable Name**: The name of the variable, following camelCase convention.
- **Value**: An optional initial value assigned to the variable.

### Examples
```java
int age = 25;        // Integer variable
double salary = 5000.50;  // Double variable
String name = "John";    // String variable
```

### Comparison with C
In C, you declare variables with data types like `int`, `float`, or `char`. Java expands on this with additional data types like `String` and objects. There’s no need to use pointers in Java as memory is managed automatically.

---

## Using the `Scanner` Class for Input

### What is the `Scanner` Class?
The `Scanner` class is part of Java’s `java.util` package and is used to take input from various sources, including user input from the keyboard.

### Importing the `Scanner` Class
To use the `Scanner` class, you need to import it at the beginning of your Java program:
```java
import java.util.Scanner;
```
- **Why Import Statements are Needed**: Java has a large set of libraries organized into packages. Import statements tell the compiler which classes or packages you are going to use in your program.

### Declaring and Using a `Scanner` Object
1. **Create a `Scanner` Object**:
   ```java
   Scanner scanner = new Scanner(System.in);
   ```
   - `Scanner` is the data type, similar to declaring a variable.
   - `scanner` is the name of the object.
   - `System.in` refers to standard input (keyboard).

2. **Taking Input**:
   ```java
   int number = scanner.nextInt(); // Reads an integer
   double value = scanner.nextDouble(); // Reads a double
   String text = scanner.nextLine(); // Reads a full line of text
   ```

3. **Closing the Scanner**:
   ```java
   scanner.close();
   ```
   - It's important to close the `Scanner` object after use to free up resources and avoid memory leaks.

### Why Scanners Must Be Closed
Closing the scanner ensures that the underlying input stream is properly released. Not closing it can lead to resource leaks, especially in large applications.

---

## Understanding Import Statements

### What are Import Statements?
Import statements are used to include external classes or entire packages in your Java program. This allows you to use pre-defined classes without having to write them from scratch.

### Syntax
```java
import packageName.className;
```
- **packageName**: The name of the package where the class is located.
- **className**: The specific class you want to use.

### Example
```java
import java.util.Scanner; // Imports the Scanner class
```
- This statement imports the `Scanner` class from the `java.util` package, allowing you to create `Scanner` objects in your program.

---

## Printing Variables in Java

### Printing Variables with `System.out.println()`
The `System.out.println()` method is used to print text and variables to the console. Here’s how to use it:

```java
int number = 10;
System.out.println("The number is: " + number); // Output: The number is: 10
```
- **Concatenation**: The `+` operator is used to concatenate (join) text and variables.

### Printing Multiple Variables
```java
int age = 25;
String name = "Alice";
System.out.println("Name: " + name + ", Age: " + age); // Output: Name: Alice, Age: 25
```

### Using Escape Sequences
- `\n`: New line.
- `\t`: Tab space.
- Example:
  ```java
  System.out.println("Hello\nWorld!"); // Output:
  // Hello
  // World!
  ```

---

## Practice Questions

1. **Question 1**: Write a Java program that declares a variable of each basic data type (int, double, String) and prints them using `System.out.println()`.

2. **Question 2**: What is the purpose of an import statement in Java? Why do you need to import the `Scanner` class before using it?

3. **Question 3**: Create a Java program that takes an integer input from the user using a `Scanner` object and then prints whether the number is positive, negative, or zero.

4. **Question 4**: Explain why it is important to close a `Scanner` object after use. What could happen if you don’t?

5. **Question 5**: Modify the "Hello World" program to ask the user for their name and print a personalized greeting (e.g., “Hello, Alice!”).
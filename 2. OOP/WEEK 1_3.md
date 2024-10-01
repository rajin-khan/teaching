# WEEK 1_3: Introduction to Strings and String Functions in Java

## Overview
In Java, Strings are an essential data type for handling text. Strings are used to store sequences of characters and provide a wide range of functions for manipulating and analyzing text data. This handout will cover what Strings are, how they work in Java, and how to use built-in String functions effectively.

---

## 1. **What is a String in Java?**

### Definition of a String
- A **String** in Java is an object that represents a sequence of characters. 
- Strings in Java are **immutable**, meaning once a String object is created, it cannot be modified. Any operation that modifies a String will create a new object.

### Example:
```java
String name = "Hello, World!";
```

- Here, `name` is a String variable storing the text "Hello, World!".

### Important Points:
- **Immutable**: Once created, the content of the String cannot change.
- **Reference Type**: Strings are objects in Java, not primitive data types.

---

## 2. **Declaring and Initializing Strings**

### Two Ways to Declare a String

1. **Using String Literals**: The easiest way to create a String.
   ```java
   String greeting = "Hello";
   ```

2. **Using the `new` Keyword**: Creates a new String object explicitly.
   ```java
   String message = new String("Hello");
   ```

Both methods are valid, but using String literals is more common due to the memory efficiency of Java's String pool.

---

## 3. **Commonly Used String Functions in Java**

Java provides a wide variety of methods to manipulate and work with Strings. Below are some of the most commonly used String methods.

### 1. `length()`
- **Description**: Returns the length (number of characters) of the string.
- **Syntax**: `string.length()`
- **Example**:
  ```java
  String text = "Java";
  int len = text.length(); // len will be 4
  ```

### 2. `charAt(int index)`
- **Description**: Returns the character at the specified index.
- **Syntax**: `string.charAt(index)`
- **Example**:
  ```java
  String text = "Hello";
  char ch = text.charAt(1); // ch will be 'e'
  ```

### 3. `substring(int start, int end)`
- **Description**: Returns a new string that is a substring of the original string, starting from `start` index to `end` index (exclusive).
- **Syntax**: `string.substring(start, end)`
- **Example**:
  ```java
  String text = "Java Programming";
  String part = text.substring(0, 4); // part will be "Java"
  ```

### 4. `toUpperCase()` and `toLowerCase()`
- **Description**: Converts all characters in the string to upper case or lower case.
- **Syntax**: `string.toUpperCase()` or `string.toLowerCase()`
- **Example**:
  ```java
  String text = "java";
  String upper = text.toUpperCase(); // upper will be "JAVA"
  ```

### 5. `equals()` and `equalsIgnoreCase()`
- **Description**: Compares two strings for equality. `equalsIgnoreCase()` ignores case when comparing.
- **Syntax**: `string1.equals(string2)` or `string1.equalsIgnoreCase(string2)`
- **Example**:
  ```java
  String s1 = "Java";
  String s2 = "JAVA";
  boolean result = s1.equalsIgnoreCase(s2); // result will be true
  ```

### 6. `contains()`
- **Description**: Checks if a string contains a specified sequence of characters.
- **Syntax**: `string.contains(CharSequence sequence)`
- **Example**:
  ```java
  String text = "Hello, World!";
  boolean contains = text.contains("World"); // contains will be true
  ```

### 7. `replace()`
- **Description**: Replaces all occurrences of a specified character or sequence of characters with another character or sequence.
- **Syntax**: `string.replace(oldChar, newChar)`
- **Example**:
  ```java
  String text = "Java Programming";
  String replaced = text.replace("Java", "Python"); // replaced will be "Python Programming"
  ```

### 8. `trim()`
- **Description**: Removes leading and trailing white spaces from a string.
- **Syntax**: `string.trim()`
- **Example**:
  ```java
  String text = "   Java   ";
  String trimmed = text.trim(); // trimmed will be "Java"
  ```

### 9. `split()`
- **Description**: Splits a string into an array of strings based on a specified delimiter.
- **Syntax**: `string.split(delimiter)`
- **Example**:
  ```java
  String text = "apple,banana,cherry";
  String[] fruits = text.split(","); // fruits will be ["apple", "banana", "cherry"]
  ```

---

## 4. **How to Use String Functions**

### Example: Combining String Functions
Let’s look at a simple example that demonstrates how multiple String functions can be used together.

```java
public class Main {
    public static void main(String[] args) {
        String sentence = "   Java is Fun!   ";

        // Trim the spaces
        String trimmed = sentence.trim();

        // Convert to upper case
        String upperCase = trimmed.toUpperCase();

        // Extract a substring
        String substring = upperCase.substring(0, 4); // "JAVA"

        // Check if contains a word
        boolean containsFun = upperCase.contains("FUN"); // true

        // Print the results
        System.out.println("Trimmed: " + trimmed);
        System.out.println("UpperCase: " + upperCase);
        System.out.println("Substring: " + substring);
        System.out.println("Contains 'FUN': " + containsFun);
    }
}
```

### Explanation:
- **`trim()`**: Removes leading and trailing spaces.
- **`toUpperCase()`**: Converts the entire string to upper case.
- **`substring()`**: Extracts the substring "JAVA".
- **`contains()`**: Checks if "FUN" is present in the string.

---

## 5. **Practice Questions**

1. Write a Java program to input a string and check if it contains the word "Java". Use the `contains()` method.

2. Create a Java program that takes a string, converts it to upper case, and prints the number of characters in the string using the `length()` method.

3. Write a Java program to take a full sentence as input, remove all the spaces using the `replace()` method, and print the modified string.

4. Create a program that splits a comma-separated list of fruits ("apple,banana,orange") into individual strings and prints each one using a `for` loop.

5. Write a Java program to input a string, extract a substring from the 3rd character to the 8th character using the `substring()` method, and print the result.

---
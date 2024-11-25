### **WEEK 4_1: Errors, Exceptions, and Try-Catch Blocks in Java**

---

### **Introduction**
Errors and exceptions are integral to programming in Java. They help identify issues during runtime and ensure programs handle unexpected situations gracefully. 

---

### **Errors vs Exceptions**
- **Errors**: Represent serious problems that a reasonable application should not try to catch. Example: `OutOfMemoryError`.
- **Exceptions**: Issues that can be handled during program execution. Examples: `IOException`, `ArithmeticException`.

---

### **Keywords and Definitions**
1. **Exception Handling**: Mechanism to handle runtime errors and maintain program flow.
2. **Try-Catch Block**: Used to catch exceptions and define alternative actions.
3. **Finally Block**: Optional block that always executes, used for cleanup.
4. **Throw**: Keyword to explicitly throw an exception.
5. **Throws**: Used in method signatures to declare exceptions the method can throw.

---

### **Types of Exceptions**
1. **Checked Exceptions**:
   - Detected during compile-time.
   - Must be handled using a try-catch block or declared using `throws`.
   - Example: `IOException`, `SQLException`.
   
2. **Unchecked Exceptions**:
   - Occur during runtime.
   - Examples: `NullPointerException`, `ArithmeticException`.

3. **Errors**:
   - Non-recoverable, system-level issues.
   - Example: `StackOverflowError`, `OutOfMemoryError`.

---

### **Basic Exception Hierarchy**
- `Throwable`: Parent class for all exceptions and errors.
  - `Exception`: Recoverable issues.
  - `Error`: Irrecoverable issues.

---

### **How Try-Catch Blocks Work**
The basic structure:
```java
try {
    // Code that might throw an exception.
} catch (ExceptionType e) {
    // Code to handle the exception.
}
```
Explanation:
- **`try`**: Contains code that might throw an exception.
- **`catch`**: Handles the exception.
- **`e`**: Object of the exception that contains details of the error.

---

### **Multiple Catch Blocks**
You can use multiple `catch` blocks to handle different types of exceptions:
```java
try {
    // Risky code
} catch (IOException e) {
    System.out.println("Input-output error occurred.");
} catch (ArithmeticException e) {
    System.out.println("Arithmetic error occurred.");
}
```

---

### **Finally Block**
Used for cleanup operations:
```java
try {
    // Risky code
} catch (Exception e) {
    System.out.println("Exception handled.");
} finally {
    System.out.println("This block always executes.");
}
```

---

### **Throw and Throws**
1. **`throw`**: Used to explicitly throw an exception.
   ```java
   throw new IllegalArgumentException("Invalid argument!");
   ```

2. **`throws`**: Declares exceptions a method might throw.
   ```java
   public void readFile() throws IOException {
       // Method body
   }
   ```

---

### **Ways to Print Exceptions**
1. **`getMessage()`**: Returns a detailed error message.
2. **`printStackTrace()`**: Prints the exception stack trace.
3. **Custom Messages**: You can add custom exception messages in the `catch` block.

---

### **Code Examples**

#### **Basic Try-Catch Block**
```java
public class Main {
    public static void main(String[] args) {
        try {
            int result = 10 / 0; // ArithmeticException
        } catch (ArithmeticException e) {
            System.out.println("Error: Division by zero.");
        }
    }
}
```

#### **Multiple Catch Blocks**
```java
public class MultipleCatchExample {
    public static void main(String[] args) {
        try {
            String str = null;
            System.out.println(str.length()); // NullPointerException
        } catch (NullPointerException e) {
            System.out.println("Null Pointer Exception caught.");
        } catch (Exception e) {
            System.out.println("General exception caught.");
        }
    }
}
```

#### **Finally Block**
```java
public class FinallyExample {
    public static void main(String[] args) {
        try {
            int[] numbers = {1, 2, 3};
            System.out.println(numbers[5]); // ArrayIndexOutOfBoundsException
        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("Index out of bounds.");
        } finally {
            System.out.println("Finally block executed.");
        }
    }
}
```

#### **Throw Keyword**
```java
public class ThrowExample {
    public static void checkAge(int age) {
        if (age < 18) {
            throw new IllegalArgumentException("Age must be 18 or older.");
        }
        System.out.println("Age is valid.");
    }

    public static void main(String[] args) {
        checkAge(15);
    }
}
```

#### **Throws Keyword**
```java
import java.io.File;
import java.io.FileNotFoundException;
import java.util.Scanner;

public class ThrowsExample {
    public void readFile() throws FileNotFoundException {
        File file = new File("nonexistent.txt");
        Scanner scanner = new Scanner(file);
    }

    public static void main(String[] args) {
        ThrowsExample example = new ThrowsExample();
        try {
            example.readFile();
        } catch (FileNotFoundException e) {
            System.out.println("File not found.");
        }
    }
}
```

---

### **Importance of Exception Handling**
1. Prevents program crashes.
2. Helps in debugging by providing detailed error messages.
3. Ensures resource cleanup (e.g., closing files).

---

### **Practice Questions**

1. Write a program that takes two integers as input and divides the first by the second. Use exception handling to manage `ArithmeticException` (division by zero).
2. Create a method that throws an `IllegalArgumentException` if the input string is empty. Use `throw` and `throws`.
3. Write a program that reads a file using `Scanner`. Handle `FileNotFoundException`.
4. Implement a program with multiple catch blocks to handle `ArrayIndexOutOfBoundsException` and `NullPointerException`.
5. Write a program that uses a `finally` block to ensure a resource (e.g., a file or database connection) is closed properly.


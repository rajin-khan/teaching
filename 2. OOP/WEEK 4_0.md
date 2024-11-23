### **WEEK 4_0: File Handling in Java**

---

### **Introduction**
File handling is a core concept in Java that allows programs to create, read, write, and manipulate files. This feature is crucial for storing data permanently and managing resources efficiently.

---

### **Keywords and Definitions**
- **File Handling**: The process of creating, reading, writing, and managing files through code.
- **File**: A resource for storing information (e.g., text, data, or binary content).
- **Stream**: A sequence of data used for file input (reading) or output (writing).
- **FileReader/FileWriter**: Classes for handling text files.
- **BufferedReader/BufferedWriter**: Efficient classes for reading/writing files with buffering.
- **Scanner**: Used for reading files.
- **PrintWriter**: Writes formatted data to files.
- **IOException**: An exception for handling input-output-related errors.

---

### **Why File Handling is Useful**
1. **Data Storage**: Retains data even after the program ends.
2. **Data Sharing**: Allows file transfer between systems.
3. **Logs**: Maintains records of operations, errors, or activities.
4. **Configuration**: Reads external settings for the application.

---

### **Basic File Handling Operations**
1. **Creating a File**
   - Use the `File` class and `createNewFile()` method.
   - Example: Creating a text file.

2. **Writing to a File**
   - Use classes like `FileWriter`, `BufferedWriter`, or `PrintWriter`.

3. **Reading from a File**
   - Use classes like `FileReader`, `BufferedReader`, or `Scanner`.

4. **Deleting a File**
   - Use the `delete()` method from the `File` class.

---

### **Getting Started with File Handling in Java**

#### **1. Creating a File**
```java
import java.io.File;
import java.io.IOException;

public class FileCreationExample {
    public static void main(String[] args) {
        File file = new File("example.txt");
        try {
            if (file.createNewFile()) {
                System.out.println("File created: " + file.getName());
            } else {
                System.out.println("File already exists.");
            }
        } catch (IOException e) {
            System.out.println("An error occurred.");
            e.printStackTrace();
        }
    }
}
```
**Explanation**:
- `File`: Represents a file/directory in the system.
- `createNewFile()`: Creates a new file if it doesn’t already exist.

---

#### **2. Writing to a File**
```java
import java.io.FileWriter;
import java.io.IOException;

public class FileWriteExample {
    public static void main(String[] args) {
        try {
            FileWriter writer = new FileWriter("example.txt");
            writer.write("Hello, World!");
            writer.close();
            System.out.println("Successfully wrote to the file.");
        } catch (IOException e) {
            System.out.println("An error occurred.");
            e.printStackTrace();
        }
    }
}
```
**Explanation**:
- `FileWriter`: Writes characters to files.
- `write()`: Writes text to the file.
- `close()`: Closes the file to free resources.

---

#### **3. Reading from a File**
Using `Scanner`:
```java
import java.io.File;
import java.io.FileNotFoundException;
import java.util.Scanner;

public class FileReadExample {
    public static void main(String[] args) {
        try {
            File file = new File("example.txt");
            Scanner scanner = new Scanner(file);
            while (scanner.hasNextLine()) {
                String line = scanner.nextLine();
                System.out.println(line);
            }
            scanner.close();
        } catch (FileNotFoundException e) {
            System.out.println("An error occurred.");
            e.printStackTrace();
        }
    }
}
```
**Explanation**:
- `Scanner`: Reads files line by line.
- `hasNextLine()`: Checks if more lines exist.
- `nextLine()`: Reads the next line.

---

#### **4. Deleting a File**
```java
import java.io.File;

public class FileDeleteExample {
    public static void main(String[] args) {
        File file = new File("example.txt");
        if (file.delete()) {
            System.out.println("Deleted the file: " + file.getName());
        } else {
            System.out.println("Failed to delete the file.");
        }
    }
}
```
**Explanation**:
- `delete()`: Removes the file.

---

#### **5. Buffered File Operations**
Using `BufferedWriter` and `BufferedReader` for efficiency:
- **Writing**:
  ```java
  import java.io.BufferedWriter;
  import java.io.FileWriter;
  import java.io.IOException;

  public class BufferedWriteExample {
      public static void main(String[] args) {
          try {
              BufferedWriter writer = new BufferedWriter(new FileWriter("example.txt"));
              writer.write("This is buffered writing.");
              writer.close();
              System.out.println("Successfully wrote to the file.");
          } catch (IOException e) {
              System.out.println("An error occurred.");
              e.printStackTrace();
          }
      }
  }
  ```
- **Reading**:
  ```java
  import java.io.BufferedReader;
  import java.io.FileReader;
  import java.io.IOException;

  public class BufferedReadExample {
      public static void main(String[] args) {
          try {
              BufferedReader reader = new BufferedReader(new FileReader("example.txt"));
              String line;
              while ((line = reader.readLine()) != null) {
                  System.out.println(line);
              }
              reader.close();
          } catch (IOException e) {
              System.out.println("An error occurred.");
              e.printStackTrace();
          }
      }
  }
  ```

---

### **Common File Handling Methods**
| **Method**               | **Purpose**                                   |
|---------------------------|-----------------------------------------------|
| `createNewFile()`         | Creates a new file.                          |
| `exists()`                | Checks if a file exists.                     |
| `delete()`                | Deletes a file.                              |
| `write()`                 | Writes text to a file.                       |
| `readLine()` (Buffered)   | Reads a single line from a file.             |
| `hasNextLine()` (Scanner) | Checks if there’s another line to read.      |
| `close()`                 | Closes the file to release resources.        |

---

### **Best Practices**
1. Always close streams (`close()`).
2. Use `try-catch` blocks to handle `IOException`.
3. Avoid hardcoding file paths; use relative paths for portability.

---

### **Practice Questions**

1. Write a program to create a file, write "Hello, File Handling!" into it, and read the content back.
2. Create a file and use `BufferedWriter` to write 5 lines of text. Then use `BufferedReader` to read and print the lines.
3. Write a program that checks if a file exists. If it exists, delete it; otherwise, create a new one.
4. Write a program that appends text to an existing file without overwriting its content.
5. Create a program that reads and counts the number of lines in a given text file.
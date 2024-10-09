# WEEK 2_1: Attributes, Methods, and Constructors in Java

## Introduction

In Java, **attributes**, **methods**, and **constructors** are fundamental building blocks for creating classes and objects. They define how an object behaves and what data it holds. Understanding these concepts is key to writing effective and organized Java programs.

---

## 1. **Attributes**

### Definition:
- **Attributes** (also called **fields** or **properties**) are variables that belong to a class and describe the properties of an object.
- These variables define the **state** of an object and can be of any data type (e.g., `int`, `String`, `boolean`).

### Syntax:
```java
class Car {
    String model;  // Attribute
    int year;      // Attribute
}
```

### Important Points:
- **Scope**: Attributes are usually declared at the top of a class, outside methods.
- **Access Modifiers**: The access to attributes is often controlled by modifiers such as `private`, `public`, or `protected`.

### Example:
```java
class Car {
    String brand = "Toyota";
    int speed = 120;
}
```

In this example, `brand` and `speed` are attributes of the `Car` class.

---

## 2. **Methods**

### Definition:
- **Methods** are functions defined inside a class that describe the **behavior** of an object. They perform actions or operations on the object's attributes.

### Syntax:
```java
class Car {
    void displayInfo() {
        System.out.println("Car is running.");
    }
}
```

### Important Points:
- **Return Type**: Every method in Java has a return type (`void` if it returns nothing).
- **Method Signature**: A method includes the method name, return type, and parameters (if any).
- **Parameters**: Methods can accept input values (called parameters) to perform actions.

### Example:
```java
class Car {
    String brand = "Toyota";
    int speed = 120;
    
    // Method to display car's information
    void displayInfo() {
        System.out.println("Brand: " + brand);
        System.out.println("Speed: " + speed);
    }
}
```

Here, the `displayInfo` method prints the car's `brand` and `speed`.

---

## 3. **Constructors**

### Definition:
- A **constructor** is a special type of method that is used to **initialize** objects. It is called automatically when an object of a class is created.

### Syntax:
- Constructors have the same name as the class and **do not have a return type**.
```java
class Car {
    Car() {
        // Constructor code
    }
}
```

### Important Points:
- **Default Constructor**: If no constructor is defined, Java provides a default constructor.
- **Parameterized Constructor**: A constructor that accepts parameters to initialize an object’s attributes.

### Example:
```java
class Car {
    String brand;
    int speed;
    
    // Constructor to initialize attributes
    Car(String brand, int speed) {
        this.brand = brand;   // "this" refers to the current object's attribute
        this.speed = speed;
    }
    
    void displayInfo() {
        System.out.println("Brand: " + brand);
        System.out.println("Speed: " + speed);
    }
}

public class Main {
    public static void main(String[] args) {
        // Create an object of Car class using the constructor
        Car myCar = new Car("Honda", 150);
        myCar.displayInfo();
    }
}
```

In this example:
- The constructor `Car(String brand, int speed)` initializes the attributes `brand` and `speed`.
- `myCar` is an object created with specific values ("Honda" and 150).

### Why Constructors are Useful:
- **Automatic Initialization**: Constructors are automatically called when an object is created, ensuring proper initialization.
- **Flexibility**: You can create objects with different values using constructors.

---

## 4. **Key Differences Between Methods and Constructors**

| Feature           | Methods                                      | Constructors                                   |
|-------------------|----------------------------------------------|------------------------------------------------|
| **Purpose**        | Perform specific actions on objects          | Initialize an object                           |
| **Name**           | Can be any valid identifier                  | Must be the same as the class name             |
| **Return Type**    | Can return any type or `void`                | No return type, not even `void`                |
| **When Called**    | Explicitly called on objects                 | Automatically called when an object is created |

---

## 5. **A Brief Introduction to Inheritance**

### Definition:
- **Inheritance** allows one class (child class) to inherit attributes and methods from another class (parent class). This promotes code reuse and organization.

### Example:
```java
class Vehicle {
    String brand = "Ford";
}

class Car extends Vehicle {
    int speed = 100;
}
```

In this example, `Car` inherits the `brand` attribute from the `Vehicle` class.

Inheritance will be covered in more depth in the next lesson!

---

## 6. **Practice Questions**

1. Write a Java class `Person` with attributes `name` and `age`. Create a method to display the details of the person, and a constructor to initialize the attributes.

2. Create a class `Book` with the attributes `title` and `author`. Write a constructor that takes these two values as parameters. Write a method to print the details of the book.

3. Implement a class `Dog` that has the attributes `breed` and `size`. Create a method to display the dog's information, and a constructor to initialize the attributes.

4. Create a `Student` class that has attributes `name`, `rollNumber`, and `marks`. Write a method to print the student’s details. Use a constructor to initialize the attributes.

5. Write a class `Employee` with attributes `name` and `salary`. Implement a method to display the employee’s information, and use a parameterized constructor to initialize the attributes.

---
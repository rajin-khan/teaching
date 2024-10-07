# WEEK 1_1: Introduction to Classes and Objects in Java

## Overview
Classes and objects are the building blocks of Object-Oriented Programming (OOP) in Java. Understanding these concepts is crucial for developing structured and reusable code. This handout provides an introduction to how classes and objects work, how they are defined and instantiated, and how they are used to model real-world entities in Java.

---

## 1. **Classes and Objects: A Basic Overview**

### What is a Class?
- A **class** is a blueprint or template for creating objects. It defines properties (fields) and behaviors (methods) that the objects created from the class will have.
- Think of a class like a blueprint for a house: it provides the design, but you have to build the house (object) to use it.

### What is an Object?
- An **object** is an instance of a class. It is a tangible representation of the blueprint (class) and contains actual data.
- Objects have **state** (represented by fields) and **behavior** (represented by methods).

---

## 2. **Declaring a Class**

### Basic Class Structure
In Java, a class is declared using the `class` keyword, followed by the class name. The class name should be written in **PascalCase** (e.g., `Student`, `Car`, `Person`).

#### Example of a Class
```java
public class Car {
    // Fields (also known as instance variables)
    String make;
    String model;
    int year;

    // Method (also known as a function inside a class)
    public void startEngine() {
        System.out.println("The engine is starting.");
    }
}
```

#### Breakdown of the Example:
- **Fields**: `String make`, `String model`, and `int year` represent the state of the `Car`.
- **Method**: `startEngine()` is a behavior that can be executed by the object of the `Car` class.

---

## 3. **Instantiating Objects**

### How to Create an Object
To create an object in Java, you need to **instantiate** it from a class using the `new` keyword.

#### Example of Object Creation
```java
Car myCar = new Car();
```

#### Breakdown of the Example:
- **Car**: The class type (blueprint).
- **myCar**: The object name (an instance of `Car`).
- **new Car()**: The `new` keyword allocates memory for the object, and the constructor (default constructor in this case) initializes the object.

### Accessing Fields and Methods
Once an object is created, you can access its fields and methods using the dot (`.`) operator.

#### Example
```java
myCar.make = "Toyota";
myCar.model = "Corolla";
myCar.year = 2020;
myCar.startEngine();
```
- Here, `myCar.make`, `myCar.model`, and `myCar.year` assign values to the object's fields.
- `myCar.startEngine()` calls the method to start the engine.

---

## 4. **How Classes Work Across Different Files**

### Single Class in One File
In Java, it's common to declare each class in its own file. The file name should match the class name and have the `.java` extension.

#### Example: Car.java
```java
public class Car {
    String make;
    String model;
    int year;

    public void startEngine() {
        System.out.println("The engine is starting.");
    }
}
```

#### Example: Main.java (another file)
```java
public class Main {
    public static void main(String[] args) {
        Car myCar = new Car();
        myCar.make = "Toyota";
        myCar.model = "Corolla";
        myCar.year = 2020;
        myCar.startEngine();
    }
}
```

- **File Structure**: Each class is placed in a separate file with the same name as the class. In the example, `Car.java` holds the class `Car`, while `Main.java` contains the `main()` method, where objects are created.

---

## 5. **Detailed Explanation of Concepts**

### Fields (Instance Variables)
Fields (also called instance variables) hold data specific to each object. Each object can have different values for these fields.

#### Example:
```java
myCar.make = "Toyota";  // myCar's make is Toyota
Car anotherCar = new Car();
anotherCar.make = "Honda";  // anotherCar's make is Honda
```

### Methods (Instance Methods)
Methods define the behavior of the objects. They are functions that can manipulate object data or perform operations.

#### Example:
```java
public void displayInfo() {
    System.out.println("Car make: " + make);
    System.out.println("Car model: " + model);
    System.out.println("Car year: " + year);
}
```

- This method can be used by an object to display its details:
```java
myCar.displayInfo();
```

### Constructors
A **constructor** is a special method used to initialize objects. It has the same name as the class and no return type.

#### Example of a Constructor
```java
public Car(String make, String model, int year) {
    this.make = make;
    this.model = model;
    this.year = year;
}
```
- **this**: Refers to the current object (helps avoid confusion between fields and parameters).

---

## 6. **Summary of Key Points**

- **Class**: Blueprint for creating objects. It contains fields (state) and methods (behavior).
- **Object**: An instance of a class, with its own set of data (state) and abilities (methods).
- **Instantiating an Object**: Use the `new` keyword to create an object.
- **Fields**: Variables that store data specific to each object.
- **Methods**: Define behaviors that an object can perform.
- **Constructors**: Initialize an object’s fields when it is created.
- **Accessing Fields/Methods**: Use the dot (`.`) operator to access fields and methods of an object.

---

## 7. **Practice Questions**

1. Write a Java class `Person` with fields `name`, `age`, and a method `displayInfo()` that prints the person's information. Create an object of this class in `Main` and call the method.

2. Create a class `Book` with fields `title`, `author`, and `price`. Write a constructor to initialize these fields, and create a method `displayDetails()` to print the book’s details. Create two objects of the class `Book` and print their details.

3. Write a Java program with a class `Rectangle` that has fields `length` and `width`. Add a method `calculateArea()` that returns the area of the rectangle. Create objects for two rectangles and display their areas.

4. Create a `Student` class with fields `name` and `marks`. Write a method `isPassed()` that returns `true` if the marks are greater than 50, and `false` otherwise. Instantiate a student object in the `main` method and check if the student has passed.

5. Create a class `Dog` with fields `breed`, `age`, and `color`. Write a method `bark()` that prints "Woof!" when called. Instantiate multiple `Dog` objects and call the `bark()` method for each.

---
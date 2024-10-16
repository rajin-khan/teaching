# WEEK 2_2: Setters, Getters, and Inheritance in Java

## Introduction

This handout introduces you to **Setters**, **Getters**, and **Inheritance** in Java, three important concepts for building well-structured and reusable code. By the end of this lesson, you will understand how to control access to class attributes using setters and getters, as well as how to utilize inheritance for code reuse and organization.

---

## 1. **Setters and Getters**

### What Are Setters and Getters?

- **Setters** and **Getters** are methods that allow controlled access to the attributes of a class. These methods enable **encapsulation**, one of the fundamental principles of Object-Oriented Programming (OOP).
- Encapsulation hides the internal state of an object and only allows modification or access via controlled methods (setters and getters).

### **Setters**

- A **setter** is a method used to update or modify the value of an attribute.
- Setters often include validation to ensure the values assigned to an attribute are appropriate.

### **Syntax**:
```java
public class Person {
    private String name;  // Private attribute

    // Setter method
    public void setName(String name) {
        this.name = name;
    }
}
```

### **Getters**

- A **getter** is a method used to retrieve or access the value of an attribute.
- They help ensure that the data is obtained in a controlled manner, often protecting the data from direct access.

### **Syntax**:
```java
public class Person {
    private String name;  // Private attribute

    // Getter method
    public String getName() {
        return this.name;
    }
}
```

### Why Use Setters and Getters?

- **Encapsulation**: Setters and Getters allow you to hide the internal representation of an object and control what values are assigned or accessed.
- **Validation**: You can add logic in setters to validate the data before assigning it.

### **Example**:

```java
public class Person {
    private int age;

    // Setter with validation
    public void setAge(int age) {
        if(age > 0) {
            this.age = age;
        } else {
            System.out.println("Invalid age");
        }
    }

    // Getter
    public int getAge() {
        return this.age;
    }
}

public class Main {
    public static void main(String[] args) {
        Person p = new Person();
        p.setAge(25);  // Valid age
        System.out.println("Age: " + p.getAge());
        
        p.setAge(-5);  // Invalid age
    }
}
```

In this example, the setter `setAge` ensures that age is always a positive value.

---

## 2. **Inheritance**

### What Is Inheritance?

- **Inheritance** is an OOP concept where one class (called the **subclass** or **child class**) inherits the attributes and methods of another class (called the **superclass** or **parent class**).
- Inheritance promotes **code reuse** by allowing common properties and behaviors to be shared among related classes.

### Why Use Inheritance?

- **Code Reusability**: It allows you to reuse fields and methods of an existing class.
- **Simplifies Maintenance**: Changes in a superclass automatically apply to subclasses.
- **Hierarchical Modeling**: Inheritance models real-world relationships, such as "A Car is a Vehicle."

### Syntax:
```java
class SuperClass {
    // Superclass fields and methods
    public void display() {
        System.out.println("This is the superclass.");
    }
}

class SubClass extends SuperClass {
    // Subclass inherits fields and methods from SuperClass
}
```

### **Example**:

```java
class Animal {
    String type = "Mammal";

    public void makeSound() {
        System.out.println("Animal makes a sound.");
    }
}

class Dog extends Animal {
    String breed = "Golden Retriever";

    // Overriding the makeSound method
    @Override
    public void makeSound() {
        System.out.println("Dog barks.");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog myDog = new Dog();
        System.out.println("Type: " + myDog.type);  // Inherited attribute
        myDog.makeSound();  // Overridden method
    }
}
```

### Important Points:
- The **`extends`** keyword is used to indicate that a class is inheriting from another class.
- The subclass inherits all **non-private** fields and methods of the superclass.
- A subclass can **override** methods of the superclass to provide specific behavior.
- Constructors are **not inherited**, but a subclass can call the constructor of its parent class using the `super()` keyword.

### Use Case:
Inheritance is widely used in scenarios like:
- Modeling hierarchical relationships (e.g., Employee-Manager).
- Reusing common code between related classes.
- Implementing polymorphism, where objects can take on multiple forms (covered in later lessons).

---

## 3. **Setters, Getters, and Inheritance Combined**

When using inheritance, the subclass can still use the getters and setters of the superclass to access or modify the inherited attributes. For instance, a `Dog` class that inherits from an `Animal` class can still use the setter and getter methods defined in the `Animal` class.

---

## Summary

- **Setters** allow you to modify attributes while enforcing validation rules.
- **Getters** enable controlled access to object attributes.
- **Inheritance** lets one class inherit the properties and behaviors of another, promoting code reuse and efficient hierarchical design.

---

## 4. **Practice Questions**

1. Create a class `Student` with private attributes `name` and `age`. Write getter and setter methods for both attributes.
2. Implement a `Car` class with private attributes `brand` and `speed`. Use setters and getters to control the access to these attributes. Then, create a `SportsCar` class that inherits from `Car`.
3. Write a class `Employee` with private attributes `name` and `salary`. Create setter and getter methods for both. Then, create a subclass `Manager` that adds a new attribute `department`. The `Manager` class should inherit from `Employee`.
4. Develop a class `Shape` with an attribute `color`. Create two subclasses: `Circle` and `Square`. Each subclass should have its own method to calculate the area, but they should inherit the `color` attribute from `Shape`.
5. Write a program that defines a `Person` class with attributes `name` and `age`, and uses inheritance to create a `Teacher` class that adds a `subject` attribute. Write methods to get and set these attributes.

---
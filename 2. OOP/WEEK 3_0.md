# WEEK 3_0: Inheritance in Java

## Introduction to Inheritance Theory

**Inheritance** is one of the four core principles of Object-Oriented Programming (OOP) that allows one class (subclass or derived class) to inherit fields, methods, and behaviors from another class (superclass or parent class). It establishes a parent-child relationship between classes, where the child class can reuse, modify, or extend the functionality of the parent class. 

### Key Benefits of Inheritance:
- **Reusability**: It allows the reuse of existing code without duplication.
- **Modularity**: Makes code easier to manage by grouping related properties and methods.
- **Extensibility**: You can create new classes based on existing ones, building upon them without modifying the original code.
- **Polymorphism**: Enables one interface to be used for different types of objects, enhancing flexibility.

### Basic Inheritance in Java

In Java, inheritance is achieved using the `extends` keyword. The subclass inherits all non-private fields and methods of the superclass, and it can add its own fields and methods, or override methods from the parent class.

### Syntax:
```java
class SuperClass {
    // Fields and methods
}

class SubClass extends SuperClass {
    // Fields and methods of SubClass
}
```

### Example:
```java
class Animal {
    public void eat() {
        System.out.println("This animal eats food.");
    }
}

class Dog extends Animal {
    public void bark() {
        System.out.println("The dog barks.");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.eat();  // Inherited from Animal
        dog.bark(); // Dog's own method
    }
}
```
In this example, `Dog` inherits the `eat()` method from `Animal`.

---

## The "super" Keyword

The `super` keyword in Java is used to refer to the superclass (parent class). It has two primary uses:

1. **Calling the superclass constructor**: This must be the first line in the subclass constructor, ensuring that the parent class constructor is called before any subclass-specific initialization.
   
2. **Accessing superclass methods and fields**: If the subclass overrides a method or has a field with the same name as in the superclass, `super` allows you to access the overridden method or hidden field of the parent class.

### Example 1: Calling the Superclass Constructor
```java
class Animal {
    Animal() {
        System.out.println("Animal is created.");
    }
}

class Dog extends Animal {
    Dog() {
        super(); // Calls Animal constructor
        System.out.println("Dog is created.");
    }
}
```

### Example 2: Accessing Superclass Methods
```java
class Animal {
    public void sound() {
        System.out.println("Animal makes a sound.");
    }
}

class Dog extends Animal {
    @Override
    public void sound() {
        super.sound(); // Calls the Animal's sound method
        System.out.println("Dog barks.");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.sound(); // Calls overridden method
    }
}
```

---

## Types of Inheritance in Java

1. **Single Inheritance**: One subclass inherits from one superclass.
2. **Multilevel Inheritance**: A class inherits from a class that is itself inherited from another class.
3. **Hierarchical Inheritance**: Multiple classes inherit from a single superclass.
4. **Hybrid Inheritance**: A combination of two or more types of inheritance (achieved through interfaces).
5. **Multiple Inheritance (via Interfaces)**: Java does not support multiple inheritance directly but allows it using interfaces.

---

### 1. Single Inheritance

In **single inheritance**, a subclass inherits from one superclass. This is the simplest form of inheritance.

#### Example:
```java
class Animal {
    public void eat() {
        System.out.println("This animal eats food.");
    }
}

class Dog extends Animal {
    public void bark() {
        System.out.println("The dog barks.");
    }
}
```

### 2. Multilevel Inheritance

In **multilevel inheritance**, a class is derived from a class that is also derived from another class, forming a chain.

#### Example:
```java
class Animal {
    public void eat() {
        System.out.println("This animal eats food.");
    }
}

class Dog extends Animal {
    public void bark() {
        System.out.println("The dog barks.");
    }
}

class Puppy extends Dog {
    public void weep() {
        System.out.println("The puppy weeps.");
    }
}
```

### 3. Hierarchical Inheritance

In **hierarchical inheritance**, multiple classes inherit from a single superclass.

#### Example:
```java
class Animal {
    public void eat() {
        System.out.println("This animal eats food.");
    }
}

class Dog extends Animal {
    public void bark() {
        System.out.println("The dog barks.");
    }
}

class Cat extends Animal {
    public void meow() {
        System.out.println("The cat meows.");
    }
}
```

### 4. Hybrid Inheritance

**Hybrid inheritance** is a combination of multiple types of inheritance. While Java does not support hybrid inheritance using classes (due to the **Diamond Problem**), it can be achieved using interfaces.

---

### 5. Multiple Inheritance via Interfaces

Java does not support multiple inheritance directly using classes, but it allows it using interfaces.

#### Example:
```java
interface CanRun {
    void run();
}

interface CanBark {
    void bark();
}

class Dog implements CanRun, CanBark {
    public void run() {
        System.out.println("The dog runs.");
    }

    public void bark() {
        System.out.println("The dog barks.");
    }
}
```

---
## Key Concepts in Inheritance

- **Super Class (Parent Class)**: The class whose properties and methods are inherited by another class.
- **Sub Class (Child Class)**: The class that inherits the properties and methods of another class.
- **`extends` keyword**: Used by a class to inherit from another class.
- **Method Overriding**: Subclasses can provide their own implementation of methods inherited from a superclass.
  
---

## Practice Questions

1. Write a program where a `Person` class has attributes `name` and `age`. Create a subclass `Employee` that adds an `employeeId` attribute and a method `displayEmployeeInfo()`.

2. Create a superclass `Vehicle` with an attribute `speed` and methods `start()` and `stop()`. Create two subclasses `Car` and `Bike` that inherit from `Vehicle` and override the `start()` and `stop()` methods.

3. Implement multilevel inheritance with the classes `Person`, `Student`, and `GraduateStudent`. The `GraduateStudent` class should inherit from `Student`, which in turn inherits from `Person`.

4. Write a program that demonstrates hierarchical inheritance with a superclass `Shape` and subclasses `Circle` and `Rectangle`. Each subclass should have its own method for calculating the area.

5. Create a program that demonstrates multiple inheritance using interfaces. Have an interface `Playable` with a method `play()`, and another interface `Eatable` with a method `eat()`. Write a class `Child` that implements both interfaces.



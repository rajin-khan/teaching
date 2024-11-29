### **WEEK 5_0: UML Class Diagrams and Their Use in Java and OOP**

---

### **Introduction**

Unified Modeling Language (UML) is a visual language used to design and document object-oriented systems. Class diagrams are one of the most commonly used UML diagrams, depicting the structure of a system by showing its classes, attributes, methods, and relationships.

---

### **Keywords and Definitions**

- **UML (Unified Modeling Language)**: A standardized modeling language for visualizing, specifying, and documenting software systems.
- **Class Diagram**: A UML diagram that represents the static structure of a system, showing classes, their attributes, methods, and relationships.
- **Attributes**: Variables (fields) that define the properties of a class.
- **Methods**: Functions or behaviors of a class.
- **Relationships**: Connections between classes, including **associations**, **inheritance**, **aggregation**, and **composition**.
- **Multiplicity**: Indicates how many instances of one class relate to another (e.g., 1-to-1, 1-to-many).

---

### **Why UML Class Diagrams Are Useful**

1. **Visualization**: Helps in understanding the structure of a system.
2. **Communication**: Bridges the gap between developers, designers, and stakeholders.
3. **Documentation**: Serves as a blueprint for system implementation.
4. **Design Validation**: Ensures the design adheres to OOP principles.

---

### **Structure of a UML Class Diagram**

1. **Class Representation**:
   - A class is represented as a rectangle divided into three parts:
     - **Class Name**: Top section (e.g., `Student`).
     - **Attributes**: Middle section (e.g., `name: String`).
     - **Methods**: Bottom section (e.g., `getName(): String`).

2. **Syntax**:
   - Attributes: `visibility name: dataType` (e.g., `- age: int`).
   - Methods: `visibility name(parameters): returnType` (e.g., `+ getAge(): int`).

3. **Visibility Modifiers**:
   - `+` (Public): Accessible from anywhere.
   - `-` (Private): Accessible only within the class.
   - `#` (Protected): Accessible within the class and its subclasses.

4. **Relationships**:
   - **Association**: A connection between two classes (e.g., `Customer` and `Order`).
   - **Inheritance**: A subclass inherits from a superclass (e.g., `Car` inherits `Vehicle`).
   - **Aggregation**: A "has-a" relationship where one class contains another but can exist independently (e.g., `Library` contains `Book`).
   - **Composition**: A stronger "has-a" relationship where one class cannot exist without the other (e.g., `Engine` in a `Car`).

---

### **Getting Started with UML Class Diagrams in Java**

#### **Example: Simple UML Class Diagram**
```plaintext
--------------------
|     Student      |
--------------------
| - name: String   |
| - age: int       |
--------------------
| + getName(): String  |
| + setName(name: String): void |
| + getAge(): int |
| + setAge(age: int): void |
--------------------
```

**Java Code Implementation**:
```java
public class Student {
    private String name;
    private int age;

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }
}
```

---

#### **Example: Association**
**UML Diagram**:
```plaintext
Customer <---------> Order
```
- **Code**:
```java
public class Customer {
    private String name;

    public Customer(String name) {
        this.name = name;
    }

    public String getName() {
        return name;
    }
}

public class Order {
    private String orderNumber;

    public Order(String orderNumber) {
        this.orderNumber = orderNumber;
    }

    public String getOrderNumber() {
        return orderNumber;
    }
}
```

---

#### **Example: Inheritance**
**UML Diagram**:
```plaintext
Vehicle <|--- Car
```
**Code**:
```java
public class Vehicle {
    private int speed;

    public int getSpeed() {
        return speed;
    }

    public void setSpeed(int speed) {
        this.speed = speed;
    }
}

public class Car extends Vehicle {
    private String brand;

    public String getBrand() {
        return brand;
    }

    public void setBrand(String brand) {
        this.brand = brand;
    }
}
```

---

#### **Example: Aggregation**
**UML Diagram**:
```plaintext
Library <>------ Book
```
**Code**:
```java
public class Book {
    private String title;

    public Book(String title) {
        this.title = title;
    }

    public String getTitle() {
        return title;
    }
}

public class Library {
    private List<Book> books = new ArrayList<>();

    public void addBook(Book book) {
        books.add(book);
    }

    public List<Book> getBooks() {
        return books;
    }
}
```

---

#### **Example: Composition**
**UML Diagram**:
```plaintext
Car <>--- Engine
```
**Code**:
```java
public class Engine {
    private int horsepower;

    public Engine(int horsepower) {
        this.horsepower = horsepower;
    }

    public int getHorsepower() {
        return horsepower;
    }
}

public class Car {
    private Engine engine;

    public Car(int horsepower) {
        this.engine = new Engine(horsepower);
    }

    public Engine getEngine() {
        return engine;
    }
}
```

---

### **Best Practices**
1. Use class diagrams early in the design phase.
2. Avoid cluttering diagrams; focus on key relationships and attributes.
3. Maintain alignment with actual Java code.
4. Document visibility (`+`, `-`, `#`) clearly.

---

### **Practice Questions**

1. Design a UML class diagram for a `BankAccount` class with attributes `accountNumber` and `balance`. Add methods for `deposit` and `withdraw`.
2. Create a UML class diagram and Java code for a `Person` class that has a `name` and `Address` (using aggregation).
3. Implement a UML diagram showing inheritance between `Animal` and subclasses `Dog` and `Cat`.
4. Design a UML diagram for a `University` class containing multiple `Department` objects (use composition).
5. Write Java code for a `Company` class associated with an `Employee` class. Show the relationship in UML.

---

### **Recommended Resources**
- [UML Class Diagrams Overview](https://www.lucidchart.com/pages/uml-class-diagram)
- [GeeksforGeeks - UML Basics](https://www.geeksforgeeks.org/uml-diagrams/)
- [JavaPoint UML Tutorial](https://www.javatpoint.com/uml) 
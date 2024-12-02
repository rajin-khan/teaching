
### **Answers: Week 1–5 Java Topics**

---

#### **Answer 1: Programming Basics**
```java
public class EvenOdd {
    public static void main(String[] args) {
        int number = 10; // Example number
        if (number % 2 == 0) {
            System.out.println(number + " is even.");
        } else {
            System.out.println(number + " is odd.");
        }
    }
}
```

---

#### **Answer 2: Classes and Objects**
```java
public class Circle {
    private double radius;

    public Circle(double radius) {
        this.radius = radius;
    }

    public void setRadius(double radius) {
        this.radius = radius;
    }

    public double getRadius() {
        return radius;
    }

    public double calculateArea() {
        return Math.PI * radius * radius;
    }

    public static void main(String[] args) {
        Circle circle = new Circle(5.0);
        System.out.println("Radius: " + circle.getRadius());
        System.out.println("Area: " + circle.calculateArea());
    }
}
```

---

#### **Answer 3: String Library Functions**
```java
public class StringEquality {
    public static void main(String[] args) {
        String str1 = "Hello";
        String str2 = "hello";

        if (str1.equalsIgnoreCase(str2)) {
            System.out.println("The strings are equal (ignoring case).");
        } else {
            System.out.println("The strings are not equal.");
        }
    }
}
```

---

#### **Answer 4: Inheritance**
```java
class Vehicle {
    protected String brand;
    protected int speed;

    public Vehicle(String brand, int speed) {
        this.brand = brand;
        this.speed = speed;
    }
}

class Car extends Vehicle {
    private int seats;

    public Car(String brand, int speed, int seats) {
        super(brand, speed);
        this.seats = seats;
    }

    public void displayDetails() {
        System.out.println("Brand: " + brand + ", Speed: " + speed + " km/h, Seats: " + seats);
    }

    public static void main(String[] args) {
        Car car = new Car("Toyota", 120, 5);
        car.displayDetails();
    }
}
```

---

#### **Answer 5: Exceptions**
```java
public class Division {
    public static void main(String[] args) {
        try {
            int result = 10 / 0;
            System.out.println("Result: " + result);
        } catch (ArithmeticException e) {
            System.out.println("Error: Cannot divide by zero!");
        }
    }
}
```

---

#### **Answer 6: Constructor Overloading**
```java
public class Rectangle {
    private double length;
    private double width;

    public Rectangle() {
        this.length = 1.0;
        this.width = 1.0;
    }

    public Rectangle(double length, double width) {
        this.length = length;
        this.width = width;
    }

    public double calculateArea() {
        return length * width;
    }

    public static void main(String[] args) {
        Rectangle defaultRect = new Rectangle();
        System.out.println("Default Area: " + defaultRect.calculateArea());

        Rectangle customRect = new Rectangle(5.0, 3.0);
        System.out.println("Custom Area: " + customRect.calculateArea());
    }
}
```

---

#### **Answer 7: String Manipulation**
```java
public class ReverseString {
    public static void main(String[] args) {
        String str = "Hello";
        StringBuilder reversed = new StringBuilder(str);
        System.out.println("Reversed String: " + reversed.reverse());
    }
}
```

---

#### **Answer 8: Access Modifiers**
```java
public class Person {
    private String name;

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public static void main(String[] args) {
        Person person = new Person();
        person.setName("Alice");
        System.out.println("Name: " + person.getName());
    }
}
```

---

#### **Answer 9: Nested Try-Catch**
```java
public class NestedTryCatch {
    public static void main(String[] args) {
        try {
            int[] arr = {1, 2, 3};
            try {
                System.out.println(arr[5]); // IndexOutOfBoundsException
            } catch (ArrayIndexOutOfBoundsException e) {
                System.out.println("Error: Index out of bounds!");
            }
            int result = 10 / 0; // ArithmeticException
        } catch (ArithmeticException e) {
            System.out.println("Error: Division by zero!");
        }
    }
}
```

---

#### **Answer 10: Loops with Conditions**
```java
public class EvenNumbers {
    public static void main(String[] args) {
        for (int i = 1; i <= 10; i++) {
            if (i % 2 == 0) {
                System.out.println(i);
            }
        }
    }
}
```
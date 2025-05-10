Here's a **deep overview of `class` in Java** with explanation and examples:

---

## 🔷 What is a Class in Java?

A **class** in Java is a **blueprint** for creating objects. It defines properties (fields/attributes) and behaviors (methods) that the objects of that class will have.

---

## 🔹 Basic Structure of a Java Class

```java
class ClassName {
    // Fields (Attributes)
    DataType fieldName;

    // Constructor
    ClassName() {
        // Initialization code
    }

    // Methods (Behaviors)
    ReturnType methodName() {
        // Code
    }
}
```

---

## 🔹 Example: Simple Class

```java
class Car {
    // Fields
    String color;
    int speed;

    // Constructor
    Car(String c, int s) {
        color = c;
        speed = s;
    }

    // Method
    void displayInfo() {
        System.out.println("Color: " + color + ", Speed: " + speed);
    }
}
```

### ✅ Usage

```java
public class Main {
    public static void main(String[] args) {
        Car myCar = new Car("Red", 100);  // Object created
        myCar.displayInfo();              // Method call
    }
}
```

**Output:**

```
Color: Red, Speed: 100
```

---

## 🔹 Types of Java Classes

1. **Concrete Class**

   * A normal class that can be instantiated.
   * Example: `Car`, `Student`, etc.

2. **Abstract Class**

   * Declared with `abstract` keyword. Cannot be instantiated.
   * May have abstract methods.

   ```java
   abstract class Shape {
       abstract void draw();  // abstract method
   }

   class Circle extends Shape {
       void draw() {
           System.out.println("Drawing Circle");
       }
   }
   ```

3. **Final Class**

   * Cannot be extended (inherited).
   * Declared using `final`.

   ```java
   final class Constants {
       static final double PI = 3.14;
   }
   ```

4. **Static Nested Class**

   * Class defined inside another class and declared as static.

   ```java
   class Outer {
       static class Inner {
           void msg() {
               System.out.println("Static Inner Class");
           }
       }
   }
   ```

5. **Inner Class / Non-static Nested Class**

   * Accesses members of outer class.

   ```java
   class Outer {
       int x = 10;
       class Inner {
           void show() {
               System.out.println("x = " + x);
           }
       }
   }
   ```

6. **Anonymous Class**

   * Class without a name, often used in method calls.

   ```java
   Runnable r = new Runnable() {
       public void run() {
           System.out.println("Anonymous Class Run");
       }
   };
   ```

---

## 🔹 Key Concepts with Class

| Concept                     | Description                                                 | Example                                                    |
| --------------------------- | ----------------------------------------------------------- | ---------------------------------------------------------- |
| **Encapsulation**           | Data hiding using private fields and public getters/setters | `private int age; public void setAge(int a) { age = a; }`  |
| **Inheritance**             | One class inherits another                                  | `class Dog extends Animal {}`                              |
| **Polymorphism**            | Many forms (method overriding/overloading)                  | `draw()` method behaves differently for `Circle`, `Square` |
| **Constructor Overloading** | Multiple constructors with different parameters             | `Car(String c)` and `Car(String c, int s)`                 |

---

## 🔹 Important Notes

* Class is not memory consuming unless an object is created.
* Class members are accessed using `.` operator.
* Constructors must have the same name as the class.
* You can create multiple objects of the same class.

---

Would you like a UML diagram of class structure or explanation of access modifiers (`private`, `public`, etc.) too?

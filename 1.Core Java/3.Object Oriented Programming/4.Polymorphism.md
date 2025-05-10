Here is a **deep overview of Polymorphism in Java** with explanation and examples:

---

## 🔷 What is Polymorphism in Java?

**Polymorphism** means "**many forms**".
In Java, it allows **objects to behave differently** based on their actual type, **even when accessed through a reference of a common superclass or interface**.

---

## 🔹 Why Use Polymorphism?

* To write **flexible and reusable code**
* To implement **dynamic behavior** at runtime
* To enable **method overriding**
* To support **interface-based programming**

---

## 🔹 Types of Polymorphism in Java

| Type                          | Description                    | Resolution Time |
| ----------------------------- | ------------------------------ | --------------- |
| **Compile-Time Polymorphism** | Achieved by method overloading | Compile time    |
| **Run-Time Polymorphism**     | Achieved by method overriding  | Runtime         |

---

## 🔸 1. Compile-Time Polymorphism (Method Overloading)

### 🔹 What It Is:

Defining **multiple methods with the same name** but different parameters (type, number, or order).

### 🔹 Example:

```java
class Calculator {
    int add(int a, int b) {
        return a + b;
    }

    double add(double a, double b) {
        return a + b;
    }

    int add(int a, int b, int c) {
        return a + b + c;
    }
}

public class Main {
    public static void main(String[] args) {
        Calculator calc = new Calculator();
        System.out.println(calc.add(5, 3));         // int version
        System.out.println(calc.add(5.5, 3.2));     // double version
        System.out.println(calc.add(1, 2, 3));      // 3-int version
    }
}
```

### ✅ Output:

```
8
8.7
6
```

---

## 🔸 2. Run-Time Polymorphism (Method Overriding)

### 🔹 What It Is:

A **subclass overrides** a method of its superclass, and **method call is resolved at runtime** using dynamic method dispatch.

### 🔹 Example:

```java
class Animal {
    void sound() {
        System.out.println("Animal makes a sound");
    }
}

class Dog extends Animal {
    void sound() {
        System.out.println("Dog barks");
    }
}

class Cat extends Animal {
    void sound() {
        System.out.println("Cat meows");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal a1 = new Dog();  // Upcasting
        Animal a2 = new Cat();  // Upcasting

        a1.sound();  // Dog's sound() is called
        a2.sound();  // Cat's sound() is called
    }
}
```

### ✅ Output:

```
Dog barks
Cat meows
```

---

## 🔹 Key Concepts in Run-Time Polymorphism

### 🔸 Upcasting

```java
Animal a = new Dog();  // Reference of parent, object of child
```

### 🔸 Dynamic Method Dispatch

Method call is resolved **at runtime** based on actual object type (`Dog` or `Cat`).

---

## 🔹 Polymorphism with Interfaces

```java
interface Shape {
    void draw();
}

class Circle implements Shape {
    public void draw() {
        System.out.println("Drawing Circle");
    }
}

class Square implements Shape {
    public void draw() {
        System.out.println("Drawing Square");
    }
}

public class Main {
    public static void main(String[] args) {
        Shape s;
        s = new Circle();
        s.draw();  // Circle's draw()

        s = new Square();
        s.draw();  // Square's draw()
    }
}
```

---

## 🔹 Method Overloading vs Overriding

| Feature         | Overloading              | Overriding                           |
| --------------- | ------------------------ | ------------------------------------ |
| Class           | Same class               | Different classes (inheritance)      |
| Parameters      | Must be different        | Must be same                         |
| Return Type     | Can be same or different | Must be same or subtype              |
| Resolution Time | Compile time             | Runtime                              |
| Keyword Used    | None                     | `@Override` annotation (recommended) |

---

## 🔚 Summary Points

* **Polymorphism** = many forms of the same method.
* **Compile-time polymorphism** uses **overloading**.
* **Run-time polymorphism** uses **overriding + upcasting**.
* Enables **flexibility**, **extensibility**, and **maintainability**.
* **Interfaces** and **abstract classes** heavily use polymorphism.

---

Would you like a diagram to visualize polymorphism in a class hierarchy or more examples with interfaces and abstract classes?

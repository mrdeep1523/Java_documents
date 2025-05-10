Here's a **deep overview of Inheritance in Java** with clear explanation and examples:

---

## 🔷 What is Inheritance in Java?

**Inheritance** is an **Object-Oriented Programming (OOP)** feature that allows a class to **acquire the properties and behaviors** (fields and methods) of another class.

It promotes:

* **Code reuse**
* **Hierarchical classification**
* **Polymorphism support**

---

## 🔹 Terminology

| Term                          | Meaning                                |
| ----------------------------- | -------------------------------------- |
| **Superclass / Parent class** | The class being inherited from         |
| **Subclass / Child class**    | The class that inherits the superclass |
| **`extends` keyword**         | Used to define inheritance             |

---

## 🔹 Basic Syntax

```java
class Superclass {
    // fields and methods
}

class Subclass extends Superclass {
    // additional fields and methods
}
```

---

## 🔹 Example

```java
// Parent class
class Animal {
    void eat() {
        System.out.println("This animal eats food.");
    }
}

// Child class
class Dog extends Animal {
    void bark() {
        System.out.println("Dog barks.");
    }
}

// Main class
public class Main {
    public static void main(String[] args) {
        Dog d = new Dog();
        d.eat();   // Inherited method
        d.bark();  // Own method
    }
}
```

**Output:**

```
This animal eats food.
Dog barks.
```

---

## 🔹 Types of Inheritance in Java

| Type             | Description                                          | Supported in Java?                                    |
| ---------------- | ---------------------------------------------------- | ----------------------------------------------------- |
| **Single**       | One child class inherits from one parent class       | ✅ Yes                                                 |
| **Multilevel**   | A class inherits from a class which inherits another | ✅ Yes                                                 |
| **Hierarchical** | Multiple classes inherit from a single parent class  | ✅ Yes                                                 |
| **Multiple**     | One class inherits from multiple classes             | ❌ Not supported directly (can be done via interfaces) |
| **Hybrid**       | Combination of two or more types                     | ❌ Not supported directly                              |

---

### 🔸 Example: Multilevel Inheritance

```java
class Animal {
    void eat() {
        System.out.println("Animal eats.");
    }
}

class Dog extends Animal {
    void bark() {
        System.out.println("Dog barks.");
    }
}

class Puppy extends Dog {
    void weep() {
        System.out.println("Puppy weeps.");
    }
}

public class Main {
    public static void main(String[] args) {
        Puppy p = new Puppy();
        p.eat();   // from Animal
        p.bark();  // from Dog
        p.weep();  // from Puppy
    }
}
```

---

## 🔹 Accessing Parent Class Members

* Subclass can **directly use** all `public` and `protected` members of parent class.
* Use `super` keyword to:

  * Access parent methods/fields
  * Call parent constructor

```java
class Parent {
    void display() {
        System.out.println("Parent class");
    }
}

class Child extends Parent {
    void display() {
        super.display(); // calls Parent's display
        System.out.println("Child class");
    }
}
```

---

## 🔹 Constructor in Inheritance

* Constructors are **not inherited**
* Child class constructor **automatically calls** the parent constructor using `super()`

```java
class A {
    A() {
        System.out.println("A constructor");
    }
}

class B extends A {
    B() {
        super(); // optional, compiler adds it
        System.out.println("B constructor");
    }
}
```

---

## 🔹 Method Overriding

Child class provides a **specific implementation** of a method already defined in parent class.

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
```

---

## 🔹 Inheritance and `Object` Class

Every class in Java **implicitly inherits** from the `Object` class if no other parent is specified.

```java
class MyClass {
    // Inherits toString(), equals(), etc. from Object
}
```

---

## 🔚 Summary Points

* Inheritance enables **code reuse** and **logical hierarchy**.
* Use `extends` for inheritance.
* Java supports single, multilevel, and hierarchical inheritance.
* Use `super` to refer to parent class.
* Constructors are not inherited but parent constructor is always called.
* Helps in **method overriding** and **polymorphism**.

---

Would you like a class hierarchy diagram to visualize multilevel inheritance or an example using interfaces for multiple inheritance?

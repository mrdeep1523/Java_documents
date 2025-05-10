Here’s a **deep overview of Method Overriding in Java**, with explanation and practical examples:

---

## 🔷 What is Method Overriding in Java?

**Method Overriding** is a feature in Java that allows a subclass to provide a **specific implementation** of a method that is already defined in its superclass.

When a subclass redefines a method from its superclass, the method in the subclass **overrides** the method in the parent class. This is a key part of **runtime polymorphism** or **dynamic method dispatch**, where the method to be invoked is determined at **runtime** based on the object type, not the reference type.

---

## 🔹 Key Features of Method Overriding

| Feature                 | Description                                                                                                              |
| ----------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| ✅ Same method signature | The method in the subclass must have the **same name, return type, and parameter list** as the method in the superclass. |
| ✅ Runtime polymorphism  | The method invoked is based on the **object type** (runtime), not the reference type (compile-time).                     |
| ✅ Inheritance required  | Overriding is only possible in an **inheritance hierarchy** (subclass inherits from superclass).                         |
| ✅ Dynamic Dispatch      | The method invocation is dynamically determined during runtime.                                                          |

---

## 🔹 Syntax

```java
class Parent {
    // Parent class method
    void display() {
        System.out.println("Display from Parent");
    }
}

class Child extends Parent {
    // Overriding the Parent class method
    @Override
    void display() {
        System.out.println("Display from Child");
    }
}
```

---

## 🔹 Example of Method Overriding

```java
class Animal {
    // Parent class method
    void sound() {
        System.out.println("Animal makes a sound");
    }
}

class Dog extends Animal {
    // Method overriding in child class
    @Override
    void sound() {
        System.out.println("Dog barks");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal animal = new Animal();  // Parent object
        animal.sound();  // Calls Animal's sound()

        Dog dog = new Dog();  // Child object
        dog.sound();  // Calls Dog's overridden sound()
    }
}
```

**Output:**

```
Animal makes a sound
Dog barks
```

---

## 🔹 Important Rules for Method Overriding

1. **Same Method Signature**: The overridden method in the subclass must have the same name, return type, and parameter list as in the parent class.

2. **Access Modifiers**:

   * The overriding method in the subclass cannot have **more restrictive** access than the method in the superclass. For example, if the superclass method is `public`, the subclass method must also be `public`.
   * You can make the access level **wider**, but not narrower (e.g., `protected` method in the superclass can be overridden as `public` in the subclass).

3. **`@Override` Annotation**: It’s **not mandatory**, but it helps the compiler catch errors. If the method in the subclass does not correctly override the parent method, it will generate a compile-time error.

4. **Method Return Type**: The return type of the overridden method must be the **same** or **covariant** (i.e., a subclass type of the original return type).

5. **Cannot override `final`, `static`, or `private` methods**:

   * `final` methods cannot be overridden.
   * `static` methods are bound at compile-time, so they cannot be overridden (they are shadowed, not overridden).
   * `private` methods are not inherited, so they cannot be overridden.

---

## 🔹 Example with Return Type and Covariant Return Type

```java
class Parent {
    // Parent class method with return type String
    String getDetails() {
        return "Parent details";
    }
}

class Child extends Parent {
    // Overriding the parent method with a covariant return type
    @Override
    public String getDetails() {
        return "Child details";
    }
}

public class Main {
    public static void main(String[] args) {
        Parent p = new Parent();
        System.out.println(p.getDetails());  // Parent details

        Parent c = new Child();
        System.out.println(c.getDetails());  // Child details
    }
}
```

**Output:**

```
Parent details
Child details
```

---

## 🔹 Method Overriding vs Method Overloading

| Feature      | Method Overriding                                     | Method Overloading                                            |
| ------------ | ----------------------------------------------------- | ------------------------------------------------------------- |
| Purpose      | Changing method behavior in subclass                  | Providing multiple methods with the same name                 |
| Parameters   | Same method signature (name, return type, parameters) | Different method signatures (number/type/order of parameters) |
| Polymorphism | **Runtime polymorphism** (determined at runtime)      | **Compile-time polymorphism** (resolved at compile time)      |
| Inheritance  | Involves inheritance and class hierarchy              | No inheritance required                                       |

---

## 🔹 Why Use Method Overriding?

1. **Runtime Polymorphism**: It allows Java to decide which method to call at **runtime** (dynamic dispatch), enabling more flexible and reusable code.

2. **Custom Behavior**: Subclasses can provide their own implementation of methods defined in the superclass, allowing for **customized behavior**.

3. **Extend Parent Behavior**: Overriding methods allows child classes to **extend or modify** the functionality of parent methods without modifying the parent class code.

---

## 🔹 `super` and Method Overriding

The `super` keyword can be used to call the method from the superclass inside the overridden method in the subclass.

```java
class Parent {
    void display() {
        System.out.println("Display from Parent");
    }
}

class Child extends Parent {
    @Override
    void display() {
        super.display();  // Calls Parent's display() method
        System.out.println("Display from Child");
    }
}

public class Main {
    public static void main(String[] args) {
        Child c = new Child();
        c.display();
    }
}
```

**Output:**

```
Display from Parent
Display from Child
```

---

## 🔚 Summary Points

* **Method Overriding** allows subclasses to **provide a specific implementation** of a method defined in the superclass.
* It is a form of **runtime polymorphism**, where the method invoked is based on the **object type** (not the reference type).
* The **same method signature** must be maintained between the overridden method and the overriding method.
* **Overriding** is an important concept for creating flexible and reusable object-oriented code.

---

Would you like to see how method overriding interacts with interfaces or abstract classes?

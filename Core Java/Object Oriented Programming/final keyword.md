Here’s a **deep overview of the `final` keyword in Java**, with a detailed explanation and examples:

---

## 🔷 What is the `final` Keyword in Java?

The `final` keyword in Java is used to define constants, prevent method overriding, and prevent inheritance. It is a modifier that can be applied to:

* **Variables**: To define constants.
* **Methods**: To prevent method overriding.
* **Classes**: To prevent class inheritance.

---

## 🔹 Key Uses of the `final` Keyword

| Use Case              | Description                                                                     |
| --------------------- | ------------------------------------------------------------------------------- |
| ✅ **Final Variables** | Used to define **constant values** that cannot be changed after initialization. |
| ✅ **Final Methods**   | Used to prevent **method overriding** in subclasses.                            |
| ✅ **Final Classes**   | Used to prevent **inheritance** by making a class non-extendable.               |

---

## 🔹 1. **Final Variables**

When a variable is declared as `final`, its value cannot be changed once it has been initialized. This is often used to define **constants**.

### Example: Using `final` with Variables

```java
class Circle {
    final double PI = 3.14159;  // PI is a constant

    double area(double radius) {
        return PI * radius * radius;
    }
}

public class Main {
    public static void main(String[] args) {
        Circle circle = new Circle();
        System.out.println("Area of circle: " + circle.area(5));
        
        // Uncommenting the next line will cause a compile-time error
        // circle.PI = 3.14;  // Error: cannot assign a value to final variable PI
    }
}
```

**Output:**

```
Area of circle: 78.53975
```

In this example, the `PI` variable is marked as `final`, making it a constant. Attempting to change its value after initialization (such as `circle.PI = 3.14;`) results in a compile-time error.

---

## 🔹 2. **Final Methods**

A `final` method cannot be **overridden** by any subclass. This is useful when you want to ensure that the implementation of a method remains consistent across all subclasses.

### Example: Using `final` with Methods

```java
class Animal {
    final void sound() {
        System.out.println("Animal makes a sound");
    }
}

class Dog extends Animal {
    // Uncommenting the next line will cause a compile-time error
    // void sound() { System.out.println("Dog barks"); }  // Error: cannot override final method
}

public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.sound();  // Calls the final method from the Animal class
    }
}
```

**Output:**

```
Animal makes a sound
```

In this example, the `sound()` method in the `Animal` class is marked as `final`, so it cannot be overridden in the `Dog` class. Attempting to override the `sound()` method in `Dog` would result in a compile-time error.

---

## 🔹 3. **Final Classes**

A `final` class cannot be **subclassed** (i.e., it cannot be extended). This is used when you want to prevent a class from being inherited.

### Example: Using `final` with Classes

```java
final class Vehicle {
    void start() {
        System.out.println("Vehicle is starting");
    }
}

// Uncommenting the next line will cause a compile-time error
// class Car extends Vehicle {}  // Error: cannot inherit from final Vehicle

public class Main {
    public static void main(String[] args) {
        Vehicle v = new Vehicle();
        v.start();
    }
}
```

**Output:**

```
Vehicle is starting
```

In this example, the `Vehicle` class is marked as `final`, so it cannot be extended by any other class, such as `Car`. Trying to subclass `Vehicle` would result in a compile-time error.

---

## 🔹 4. **Final Parameters**

You can also declare **method parameters** as `final`. This ensures that the parameter cannot be modified within the method body.

### Example: Using `final` with Method Parameters

```java
class MathOperations {
    void calculateSum(final int a, final int b) {
        // a = a + 1;  // Error: cannot assign a value to final variable a
        System.out.println("Sum: " + (a + b));
    }
}

public class Main {
    public static void main(String[] args) {
        MathOperations math = new MathOperations();
        math.calculateSum(10, 20);
    }
}
```

**Output:**

```
Sum: 30
```

In this example, the parameters `a` and `b` are marked as `final`, which means they cannot be modified within the `calculateSum` method. Any attempt to modify them (e.g., `a = a + 1;`) will result in a compile-time error.

---

## 🔹 5. **Final with Inheritance and Polymorphism**

A `final` variable or method can still be used in inheritance, but its behavior is restricted. For example, you cannot override a `final` method or change a `final` variable.

### Example: `final` Variables in Inheritance

```java
class Animal {
    final String species = "Mammal";  // Constant field in parent class
}

class Dog extends Animal {
    // Cannot override 'species' because it's final in Animal class
}

public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog();
        System.out.println("Species: " + dog.species);  // Inherited final field
    }
}
```

**Output:**

```
Species: Mammal
```

In this example, the `species` field is `final` in the `Animal` class, and it is inherited by the `Dog` class. However, since it is `final`, the `Dog` class cannot change or override the value of `species`.

---

## 🔹 Summary of Key Points

1. **Final Variables**:

   * A `final` variable cannot be modified once it is initialized.
   * Often used to define constants.

2. **Final Methods**:

   * A `final` method cannot be overridden by subclasses.
   * Ensures the method's implementation remains the same.

3. **Final Classes**:

   * A `final` class cannot be subclassed.
   * Prevents inheritance, ensuring the class cannot be extended.

4. **Final Parameters**:

   * A `final` parameter cannot be modified within the method.
   * Useful to ensure parameters remain constant during method execution.

---

Would you like to see any advanced examples involving the `final` keyword, such as in **concurrent programming** or **immutable objects**?

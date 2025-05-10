Here’s a **deep overview of the `super` keyword in Java**, with a detailed explanation and examples:

---

## 🔷 What is the `super` Keyword in Java?

The `super` keyword in Java is used to refer to the **immediate parent class** of a class. It is commonly used to:

1. **Access parent class methods**.
2. **Access parent class constructors**.
3. **Access parent class fields** (instance variables).

---

## 🔹 Key Features of the `super` Keyword

| Feature                      | Description                                                                                                              |
| ---------------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| ✅ Refers to the parent class | `super` refers to the immediate **parent class** (one level up in the inheritance hierarchy).                            |
| ✅ Access parent methods      | `super` can be used to call methods defined in the parent class.                                                         |
| ✅ Access parent constructors | `super()` can be used to call a parent class constructor from a subclass constructor.                                    |
| ✅ Access parent fields       | `super` can be used to access fields (instance variables) of the parent class, especially when there is a name conflict. |

---

## 🔹 Syntax

```java
super.<method_name>   // Calls a parent class method
super(<arguments>)    // Calls a parent class constructor
super.<field_name>    // Accesses a parent class field (variable)
```

---

## 🔹 Uses of the `super` Keyword

1. **Calling Parent Class Methods**:
   `super` can be used to call a method from the parent class that has been overridden in the subclass.

2. **Accessing Parent Class Constructors**:
   `super()` can be used to invoke a constructor of the parent class from a subclass constructor.

3. **Accessing Parent Class Fields**:
   `super` can be used to reference fields from the parent class if there is a name conflict with subclass fields.

---

## 🔸 1. Calling Parent Class Methods

If a subclass overrides a method from its parent class, you can use `super` to call the parent class method.

### Example: Calling Parent Method

```java
class Animal {
    void sound() {
        System.out.println("Animal makes a sound");
    }
}

class Dog extends Animal {
    @Override
    void sound() {
        super.sound();  // Calls the parent class method
        System.out.println("Dog barks");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.sound();  // Calls the Dog class sound method, which calls the Animal class sound method
    }
}
```

**Output:**

```
Animal makes a sound
Dog barks
```

In this example, the `sound()` method in the `Dog` class overrides the `sound()` method in the `Animal` class. However, `super.sound()` is used to invoke the parent class method before executing the child class method.

---

## 🔸 2. Accessing Parent Class Constructors

The `super()` keyword is used in a subclass constructor to call the parent class's constructor. If no constructor is explicitly defined in the parent class, Java automatically calls the default constructor of the parent class.

### Example: Calling Parent Constructor

```java
class Animal {
    Animal(String name) {
        System.out.println("Animal name: " + name);
    }
}

class Dog extends Animal {
    Dog(String name) {
        super(name);  // Calls the constructor of the parent class Animal
        System.out.println("Dog created: " + name);
    }
}

public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog("Buddy");
    }
}
```

**Output:**

```
Animal name: Buddy
Dog created: Buddy
```

In this example, the constructor of the `Dog` class uses `super(name)` to call the constructor of the `Animal` class, passing the `name` argument.

---

## 🔸 3. Accessing Parent Class Fields

If a field in a subclass has the same name as a field in the parent class, `super` can be used to differentiate between the parent class field and the subclass field.

### Example: Accessing Parent Field

```java
class Animal {
    String name = "Animal";
}

class Dog extends Animal {
    String name = "Dog";

    void display() {
        System.out.println("Name in Dog class: " + name);  // Refers to Dog's name
        System.out.println("Name in Animal class: " + super.name);  // Refers to Animal's name using super
    }
}

public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.display();
    }
}
```

**Output:**

```
Name in Dog class: Dog
Name in Animal class: Animal
```

In this example, both the `Dog` and `Animal` classes have a `name` field. By using `super.name`, the `Dog` class refers to the `name` field of the `Animal` class.

---

## 🔹 Constructor Chaining with `super()`

When a class inherits from another class, the subclass constructor automatically calls the constructor of the parent class. If no constructor is explicitly defined in the parent class, Java calls the default constructor. You can explicitly call a parent constructor using `super()`.

### Example: Constructor Chaining

```java
class Vehicle {
    Vehicle() {
        System.out.println("Vehicle constructor called");
    }
}

class Car extends Vehicle {
    Car() {
        super();  // Calls Vehicle constructor explicitly
        System.out.println("Car constructor called");
    }
}

public class Main {
    public static void main(String[] args) {
        Car car = new Car();
    }
}
```

**Output:**

```
Vehicle constructor called
Car constructor called
```

Here, the `super()` call in the `Car` constructor explicitly invokes the constructor of the `Vehicle` class, which is the parent class.

---

## 🔹 Summary of Key Points

1. **Refers to the parent class**: The `super` keyword refers to the **immediate parent class** and helps access parent class methods, fields, and constructors.

2. **Access parent methods**: Use `super.methodName()` to invoke a method from the parent class, even if it is overridden in the subclass.

3. **Call parent class constructor**: `super()` is used to call a parent class constructor from the subclass constructor. It must be the first statement in the subclass constructor.

4. **Resolve name conflicts**: If both the subclass and parent class have fields with the same name, `super.fieldName` can be used to access the parent class field.

---

Would you like to see more advanced examples, such as using `super` with interfaces or in cases with multiple inheritance scenarios (using interfaces)?

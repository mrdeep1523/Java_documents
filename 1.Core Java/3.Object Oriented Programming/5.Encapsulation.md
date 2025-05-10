Here is a **deep overview of Encapsulation in Java** with clear explanation and practical examples:

---

## 🔷 What is Encapsulation in Java?

**Encapsulation** is one of the **four fundamental OOP principles** (along with Inheritance, Polymorphism, and Abstraction).

It means **wrapping data (variables) and methods (functions) together into a single unit (class)**, and **restricting direct access** to some of the object’s components.

---

## 🔹 Key Features of Encapsulation

| Feature             | Description                                                           |
| ------------------- | --------------------------------------------------------------------- |
| ✅ Data hiding       | Internal object data is hidden from outside access                    |
| ✅ Controlled access | Data is accessed only via public **getters** and **setters**          |
| ✅ Maintainability   | Easier to modify internal implementation without affecting other code |
| ✅ Security          | Prevents unauthorized access and invalid data updates                 |

---

## 🔹 How to Achieve Encapsulation in Java

1. Declare **variables as `private`**
2. Provide **public getter and setter methods** to access/update them

---

## 🔹 Encapsulation Example

```java
class Employee {
    // Private fields (data hiding)
    private String name;
    private int age;

    // Public setter
    public void setName(String n) {
        name = n;
    }

    // Public getter
    public String getName() {
        return name;
    }

    public void setAge(int a) {
        if (a > 18) {
            age = a;
        } else {
            System.out.println("Invalid age");
        }
    }

    public int getAge() {
        return age;
    }
}
```

### ✅ Using the Encapsulated Class

```java
public class Main {
    public static void main(String[] args) {
        Employee emp = new Employee();
        emp.setName("Alice");
        emp.setAge(25);

        System.out.println("Name: " + emp.getName());
        System.out.println("Age: " + emp.getAge());
    }
}
```

**Output:**

```
Name: Alice
Age: 25
```

---

## 🔹 Advantages of Encapsulation

| Advantage                      | Explanation                                                       |
| ------------------------------ | ----------------------------------------------------------------- |
| ✔ Prevents unauthorized access | Fields can’t be modified directly from outside                    |
| ✔ Improves flexibility         | Internal implementation can change without breaking external code |
| ✔ Increases control            | Validation logic can be added inside setters                      |
| ✔ Enhances maintainability     | Code is easier to debug and update                                |

---

## 🔹 Real-World Analogy

* **Encapsulation** is like a **medicine capsule**:
  You can’t see or touch the inner powder (data), but you can take the medicine via a controlled interface (getter/setter).

---

## 🔹 Without Encapsulation (Bad Practice)

```java
class Student {
    public String name;  // BAD: Exposed data
}

Student s = new Student();
s.name = "Tom";         // Direct access, no control
```

This makes it impossible to:

* Add validation
* Control access
* Track changes

---

## 🔚 Summary Points

* Encapsulation = **data + code bound together**, with **restricted access**
* Use `private` fields + `public` getters/setters
* Encourages **security**, **control**, and **clean design**
* Supports **data hiding**, which is a key part of object-oriented programming

---

Would you like me to show how encapsulation fits together with inheritance and polymorphism in a combined example?

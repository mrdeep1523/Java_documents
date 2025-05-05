Here’s a concise list of **Java Syntax Basics** to help you get started:

---

### **1. Structure of a Java Program**

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

---

### **2. Basic Syntax Elements**

* **Class Declaration**: `public class ClassName { ... }`
* **Main Method**: `public static void main(String[] args)`
* **Statements End with Semicolons**: `System.out.println("Text");`
* **Comments**:

  * Single-line: `// comment`
  * Multi-line: `/* comment */`

---

### **3. Data Types**

* **Primitive Types**:

  * Integer: `int`, `long`, `short`, `byte`
  * Floating-point: `float`, `double`
  * Character: `char`
  * Boolean: `boolean`
* **Reference Types**: e.g., `String`, `Arrays`, `Objects`

---

### **4. Variables**

```java
int age = 25;
double price = 19.99;
char grade = 'A';
boolean isJavaFun = true;
String name = "Alice";
```

---

### **5. Operators**

* **Arithmetic**: `+`, `-`, `*`, `/`, `%`
* **Relational**: `==`, `!=`, `>`, `<`, `>=`, `<=`
* **Logical**: `&&`, `||`, `!`
* **Assignment**: `=`, `+=`, `-=`, etc.

---

### **6. Control Statements**

* **If-Else**:

```java
if (x > 0) {
    // do something
} else {
    // do something else
}
```

* **Switch**:

```java
switch (day) {
    case 1: System.out.println("Monday"); break;
    default: System.out.println("Other day");
}
```

* **Loops**:

  * `for`, `while`, `do-while`

```java
for (int i = 0; i < 5; i++) {
    System.out.println(i);
}
```

---

### **7. Methods**

```java
public static int add(int a, int b) {
    return a + b;
}
```

---

### **8. Arrays**

```java
int[] numbers = {1, 2, 3, 4};
System.out.println(numbers[0]); // Output: 1
```

---

### **9. Object-Oriented Basics**

* **Class**:

```java
public class Person {
    String name;
    int age;
}
```

* **Object**:

```java
Person p = new Person();
p.name = "John";
```

* **Constructor**:

```java
public Person(String name, int age) {
    this.name = name;
    this.age = age;
}
```

* **Inheritance, Polymorphism, Abstraction, Encapsulation**: Core OOP concepts used in Java.

---

Would you like a printable cheat sheet or flashcards for quick review?

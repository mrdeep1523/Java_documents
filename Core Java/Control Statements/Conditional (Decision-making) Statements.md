Here’s a clear and concise guide to **Conditional (Decision-making) Statements in Java**:

---

## 🔹 **1. `if` Statement**

Executes block only if the condition is `true`.

```java
if (age >= 18) {
    System.out.println("You are an adult.");
}
```

---

## 🔹 **2. `if-else` Statement**

Executes one block if `true`, another if `false`.

```java
if (marks >= 50) {
    System.out.println("Pass");
} else {
    System.out.println("Fail");
}
```

---

## 🔹 **3. `if-else if-else` Ladder**

Checks multiple conditions in order.

```java
if (score >= 90) {
    System.out.println("Grade A");
} else if (score >= 75) {
    System.out.println("Grade B");
} else {
    System.out.println("Grade C");
}
```

---

## 🔹 **4. `switch` Statement**

Best for comparing a variable against multiple exact values (like `==`).

```java
int day = 3;
switch (day) {
    case 1:
        System.out.println("Monday");
        break;
    case 2:
        System.out.println("Tuesday");
        break;
    case 3:
        System.out.println("Wednesday");
        break;
    default:
        System.out.println("Other day");
}
```

> 🔸 From Java 14+, you can also use **switch expressions** with `->` and `yield`:

```java
String result = switch (grade) {
    case "A" -> "Excellent";
    case "B" -> "Good";
    default -> "Average";
};
```

---

## 🔹 **5. Ternary Operator**

Shorthand for simple `if-else`.

```java
String result = (age >= 18) ? "Adult" : "Minor";
```

---

### ✅ Tip:

* Always use `{}` braces for clarity, even in single-line `if` blocks.
* Use `switch` when dealing with multiple discrete values for better readability.

---

Would you like real-world examples using these (like grading systems, login checks, etc.)?

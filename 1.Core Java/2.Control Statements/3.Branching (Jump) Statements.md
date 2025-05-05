Here’s a clear and concise summary of **Branching (Jump) Statements in Java**:

---

## 🔀 **Branching Statements**

Used to alter the flow of execution within loops, `switch`, or blocks.

---

### 🔹 **1. `break` Statement**

* **Used to exit** a loop or `switch` block immediately.

#### ✅ In Loops:

```java
for (int i = 1; i <= 5; i++) {
    if (i == 3) break;  // loop breaks when i == 3
    System.out.println(i);
}
```

#### ✅ In `switch`:

```java
switch (day) {
    case 1: System.out.println("Monday"); break;
    case 2: System.out.println("Tuesday"); break;
    default: System.out.println("Other day");
}
```

---

### 🔹 **2. `continue` Statement**

* **Skips the current iteration** and moves to the next.

```java
for (int i = 1; i <= 5; i++) {
    if (i == 3) continue;  // skips printing 3
    System.out.println(i);
}
```

---

### 🔹 **3. `return` Statement**

* Exits from the **current method** and optionally returns a value.

```java
public static int square(int x) {
    return x * x;  // returns the result to the caller
}
```

---

### 🔹 **4. (Optional) Labeled `break`/`continue`**

* Used to break out of **nested loops** by labeling a block.

```java
outer:
for (int i = 1; i <= 3; i++) {
    for (int j = 1; j <= 3; j++) {
        if (j == 2) break outer;  // exits both loops
        System.out.println(i + " " + j);
    }
}
```

---

### ✅ Summary Table

| Statement  | Use Case                       |
| ---------- | ------------------------------ |
| `break`    | Exit loop/switch early         |
| `continue` | Skip current loop iteration    |
| `return`   | Exit method and return a value |

---

Would you like exercises to practice these statements in real scenarios?

Here’s a concise guide to **Looping (Iteration) Statements in Java**:

---

## 🔁 **1. `for` Loop**

Used when the number of iterations is known.

```java
for (int i = 1; i <= 5; i++) {
    System.out.println("Count: " + i);
}
```

---

## 🔁 **2. `while` Loop**

Used when the number of iterations is **not known**, and condition is checked **before** each loop.

```java
int i = 1;
while (i <= 5) {
    System.out.println("Count: " + i);
    i++;
}
```

---

## 🔁 **3. `do-while` Loop**

Like `while`, but guarantees at least **one execution**.

```java
int i = 1;
do {
    System.out.println("Count: " + i);
    i++;
} while (i <= 5);
```

---

## 🔁 **4. Enhanced `for-each` Loop**

Best for iterating over arrays/collections.

```java
int[] numbers = {10, 20, 30};
for (int num : numbers) {
    System.out.println(num);
}
```

---

## 🔁 **5. Loop Control Statements**

| Keyword    | Use Case                                    |
| ---------- | ------------------------------------------- |
| `break`    | Exit the loop completely                    |
| `continue` | Skip current iteration and continue looping |

```java
for (int i = 1; i <= 5; i++) {
    if (i == 3) continue;  // skips 3
    System.out.println(i);
}
```

---

### ✅ Tips:

* Use `for` when you know how many times to loop.
* Use `while`/`do-while` when the end condition depends on runtime logic.
* `for-each` is cleaner for collections/arrays.

---

Would you like a diagram or real-world examples using loops (like calculating factorials or summing arrays)?

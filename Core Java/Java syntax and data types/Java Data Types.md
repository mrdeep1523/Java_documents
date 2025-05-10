Here's a concise breakdown of **Java Data Types**:

---

## 🔹 **1. Primitive Data Types (8 types)**

These are built-in and not objects. Stored in stack memory.

| Type      | Size    | Default  | Example             | Description                     |
| --------- | ------- | -------- | ------------------- | ------------------------------- |
| `byte`    | 1 byte  | 0        | `byte b = 100;`     | Range: -128 to 127              |
| `short`   | 2 bytes | 0        | `short s = 500;`    | Range: -32,768 to 32,767        |
| `int`     | 4 bytes | 0        | `int x = 1000;`     | Most common for integers        |
| `long`    | 8 bytes | 0L       | `long l = 123L;`    | For large integers              |
| `float`   | 4 bytes | 0.0f     | `float f = 3.14f;`  | Single-precision decimal        |
| `double`  | 8 bytes | 0.0d     | `double d = 9.81;`  | Double-precision decimal        |
| `char`    | 2 bytes | '\u0000' | `char c = 'A';`     | Single 16-bit Unicode character |
| `boolean` | 1 bit   | false    | `boolean b = true;` | true or false                   |

---

## 🔹 **2. Non-Primitive / Reference Data Types**

These refer to objects and are stored in heap memory.

| Type        | Description                       | Example                    |
| ----------- | --------------------------------- | -------------------------- |
| `String`    | Sequence of characters            | `String name = "Java";`    |
| `Array`     | Fixed-size collection of elements | `int[] nums = {1, 2, 3};`  |
| `Class`     | Custom data types                 | `Person p = new Person();` |
| `Interface` | Contract for classes to implement | `Runnable r = () -> {};`   |

---

## 🔹 **Type Conversion**

* **Widening (automatic)**: `int → long → float → double`
* **Narrowing (manual)**: `double → float → long → int`

```java
int x = 10;
double y = x;           // widening
int z = (int) y;        // narrowing (casting)
```

---

Would you like a visual diagram of this or an example showing how each type is used?


---

# Polymorphism in OOP

## 1. Definition
Polymorphism means **"many forms"** — the ability of an object, method, or operator to take different forms or behave differently in different contexts.

---

## 2. Purpose
- Write **flexible** and **reusable** code.
- Handle different types of objects with a **common interface**.
- Achieve **runtime flexibility**.

---

## 3. Types of Polymorphism

### **A) Compile-time Polymorphism** (Static Binding)
- Achieved by **method overloading** or **operator overloading**.
- Resolved **at compile time**.
- **JavaScript** does not support method overloading in the same way as Java, but it can simulate it.

**Example (Java)**:
```java
class MathUtils {
    int add(int a, int b) { return a + b; }
    double add(double a, double b) { return a + b; }
}

public class Main {
    public static void main(String[] args) {
        MathUtils m = new MathUtils();
        System.out.println(m.add(5, 3));     // 8
        System.out.println(m.add(5.5, 3.2)); // 8.7
    }
}
````

**Example (JavaScript - simulated)**:

```javascript
function add(a, b, c) {
    if (c !== undefined) return a + b + c;
    return a + b;
}

console.log(add(2, 3));      // 5
console.log(add(2, 3, 4));   // 9
```

---

### **B) Runtime Polymorphism** (Dynamic Binding)

* Achieved by **method overriding**.
* Resolved **at runtime**.
* Commonly used with **inheritance**.

**Example (Java)**:

```java
class Animal {
    void sound() { System.out.println("Animal sound"); }
}
class Dog extends Animal {
    void sound() { System.out.println("Bark"); }
}
class Cat extends Animal {
    void sound() { System.out.println("Meow"); }
}

public class Main {
    public static void main(String[] args) {
        Animal a = new Dog();
        a.sound(); // Bark
        a = new Cat();
        a.sound(); // Meow
    }
}
```

**Example (JavaScript)**:

```javascript
class Animal {
    sound() { console.log("Animal sound"); }
}
class Dog extends Animal {
    sound() { console.log("Bark"); }
}
class Cat extends Animal {
    sound() { console.log("Meow"); }
}

let animals = [new Dog(), new Cat()];
animals.forEach(a => a.sound()); // Bark, Meow
```

---

## 4. Key Points

* **Method Overloading** → Same method name, different parameters (compile-time).
* **Method Overriding** → Same method name & parameters in parent/child (runtime).
* **JavaScript** → Only runtime polymorphism natively; overloading is simulated.
* Improves flexibility and maintainability.

---

## 5. Advantages

* Code reuse.
* Simplifies code by using a common interface.
* Reduces coupling.

---

## 6. Disadvantages

* Runtime polymorphism can be slightly slower due to dynamic method resolution.

```

---


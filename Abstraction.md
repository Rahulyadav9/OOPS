
---

# Abstraction in OOP

## 1. Definition
Abstraction is the **OOP principle** of hiding implementation details and showing only the **essential features** to the user.

---

## 2. Purpose
- Reduce complexity.
- Focus on **what** an object does, not **how** it does it.
- Separate **interface** from **implementation**.

---

## 3. How Abstraction is Achieved

### **In Java**
- **Abstract Classes**
- **Interfaces**

### **In JavaScript**
- Not built-in like Java, but achieved using:
  - Classes with only method definitions
  - Private fields (`#field`)
  - Closures & modules

---

## 4. Example (Java – Abstract Class)
```java
abstract class Vehicle {
    abstract void start(); // abstract method - no body

    void stop() { // concrete method
        System.out.println("Vehicle stopped");
    }
}

class Car extends Vehicle {
    void start() {
        System.out.println("Car starts with key");
    }
}

public class Main {
    public static void main(String[] args) {
        Vehicle v = new Car();
        v.start();
        v.stop();
    }
}
````

---

## 5. Example (Java – Interface)

```java
interface Animal {
    void sound(); // abstract by default
}

class Dog implements Animal {
    public void sound() {
        System.out.println("Bark");
    }
}
```

---

## 6. Example (JavaScript – Using Abstract-like Pattern)

```javascript
class Vehicle {
    constructor() {
        if (this.constructor === Vehicle) {
            throw new Error("Cannot instantiate abstract class");
        }
    }
    start() {
        throw new Error("Abstract method 'start' must be implemented");
    }
    stop() {
        console.log("Vehicle stopped");
    }
}

class Car extends Vehicle {
    start() {
        console.log("Car starts with button");
    }
}

const myCar = new Car();
myCar.start();
myCar.stop();
```

---

## 7. Key Points

* **Abstract Class**: Can have abstract & concrete methods.
* **Interface**: Only abstract methods (till Java 7), default & static methods allowed in Java 8+.
* Cannot create objects of abstract classes/interfaces.
* Forces subclasses to provide specific implementations.

---

## 8. Advantages

* Hides complex logic from the user.
* Increases code flexibility.
* Improves maintainability.

---

## 9. Disadvantages

* Increases the number of classes/files.
* Overuse can make the system harder to navigate.

---


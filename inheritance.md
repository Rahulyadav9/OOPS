---
# Inheritance in OOP

## 1. Definition
Inheritance is an **OOP concept** where a class (**child/subclass**) acquires properties and behaviors from another class (**parent/superclass**).

---

## 2. Purpose
- **Code Reusability**: Avoid rewriting common logic.
- **Extensibility**: Add or override functionality.
- **Hierarchy Modeling**: Represents real-world relationships.

---

## 3. Types of Inheritance
1. **Single** – One child inherits from one parent.
2. **Multilevel** – A class inherits from another, which inherits from another.
3. **Hierarchical** – Multiple children inherit from the same parent.
4. **Multiple** – A class inherits from multiple parents (not directly in Java, possible via interfaces).
5. **Hybrid** – Combination of the above.

---

## 4. Example (JavaScript)

```javascript
// Parent Class
class Animal {
    eat() {
        console.log("Eating...");
    }
}

// Child Class
class Dog extends Animal {
    bark() {
        console.log("Barking...");
    }
}

const dog = new Dog();
dog.eat(); // Inherited from Animal
dog.bark(); // Own method
````

---

## 5. Example (Java)

```java
class Animal {
    void eat() {
        System.out.println("Eating...");
    }
}

class Dog extends Animal {
    void bark() {
        System.out.println("Barking...");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog d = new Dog();
        d.eat(); // Inherited
        d.bark(); // Own method
    }
}
```

---

## 6. Method Overriding

A child class can **redefine** a method from the parent class.

```javascript
class Animal {
    speak() { console.log("Animal sound"); }
}

class Dog extends Animal {
    speak() { console.log("Bark"); } // Overriding
}
```

---

## 7. Key Points

* Achieved via `extends` (JS/Java).
* Supports **method overriding** for polymorphism.
* **super** keyword accesses parent class members.
* Helps DRY (Don't Repeat Yourself).

---

## 8. Advantages

* Code reuse.
* Easier maintenance.
* Logical class hierarchy.

---

## 9. Disadvantages

* Tight coupling between classes.
* Changes in parent can affect children.

```



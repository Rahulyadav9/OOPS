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


````markdown
# Types of Inheritance in OOP

## 1. Single Inheritance
**Definition**: One child inherits from one parent.

**Example (JavaScript)**:
```javascript
class Parent {
    show() { console.log("Parent class"); }
}
class Child extends Parent {
    display() { console.log("Child class"); }
}
const obj = new Child();
obj.show();   // Parent class
obj.display(); // Child class
````

---

## 2. Multilevel Inheritance

**Definition**: A class inherits from another, which inherits from another.

**Example (Java)**:

```java
class A { void methodA() { System.out.println("A"); } }
class B extends A { void methodB() { System.out.println("B"); } }
class C extends B { void methodC() { System.out.println("C"); } }

public class Test {
    public static void main(String[] args) {
        C obj = new C();
        obj.methodA(); // from A
        obj.methodB(); // from B
        obj.methodC(); // from C
    }
}
```

---

## 3. Hierarchical Inheritance

**Definition**: Multiple children inherit from the same parent.

**Example (JavaScript)**:

```javascript
class Parent {
    greet() { console.log("Hello from Parent"); }
}
class Child1 extends Parent {
    message() { console.log("Child1 here"); }
}
class Child2 extends Parent {
    message() { console.log("Child2 here"); }
}
new Child1().greet(); // Hello from Parent
new Child2().greet(); // Hello from Parent
```

---

## 4. Multiple Inheritance

**Definition**: A class inherits from multiple parents (Directly not possible in Java, but possible via interfaces; JavaScript uses mixins).

**Example (Java via Interfaces)**:

```java
interface A { void methodA(); }
interface B { void methodB(); }

class C implements A, B {
    public void methodA() { System.out.println("A"); }
    public void methodB() { System.out.println("B"); }
}
```

**Example (JavaScript via Mixins)**:

```javascript
let CanFly = Base => class extends Base {
    fly() { console.log("Flying..."); }
};
let CanSwim = Base => class extends Base {
    swim() { console.log("Swimming..."); }
};

class Animal {}
class Duck extends CanFly(CanSwim(Animal)) {}

const d = new Duck();
d.fly();
d.swim();
```

---

## 5. Hybrid Inheritance

**Definition**: Combination of two or more types of inheritance.

**Example (Java)**:

```java
interface A { void methodA(); }
class B { void methodB() { System.out.println("B"); } }
class C extends B implements A {
    public void methodA() { System.out.println("A"); }
}
class D extends C {
    void methodD() { System.out.println("D"); }
}
```

* Here:

  * `C` inherits from `B` (Single)
  * `C` implements `A` (Multiple via interface)
  * `D` inherits from `C` (Multilevel)

---

**Key Notes**:

* **JavaScript** supports single inheritance via `extends` and multiple inheritance via **mixins**.
* **Java** supports multiple inheritance **only** through interfaces, not classes.
* Hybrid inheritance is common in real-world systems but can lead to **diamond problem**.


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



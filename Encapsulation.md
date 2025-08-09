# Encapsulation in Object-Oriented Programming

## 1. Definition
Encapsulation is the **OOP concept** of **binding data (variables)** and **methods (functions)** that operate on that data into a **single unit** (class or object), while **restricting direct access** to the data.

Instead of directly accessing fields, **controlled access** is given via methods (getters and setters).

---

## 2. Purpose of Encapsulation
- **Security**: Protects sensitive data from unauthorized access.
- **Control**: Controls how the data is modified.
- **Flexibility**: Changes in internal implementation do not affect external code.
- **Maintainability**: Easier to manage and debug.

---

## 3. How Encapsulation is Achieved
| Language | Method |
|----------|--------|
| **JavaScript** | Private fields (`#`), closures, getters/setters |
| **Java** | Access modifiers (`private`, `protected`, `public`) with getters/setters |

---

## 4. Real-Life Analogy
An **ATM Machine**:  
- You can **deposit** or **withdraw** money, but you **cannot directly access** the bank's internal storage.  
- The machine's interface acts like **getter and setter methods**.

---

## 5. JavaScript vs Java Example

| **JavaScript Example** | **Java Example** |
|------------------------|------------------|
| ```javascript<br>class BankAccount {<br>    #balance; // Private field<br><br>    constructor(initialBalance) {<br>        this.#balance = initialBalance;<br>    }<br><br>    getBalance() {<br>        return this.#balance;<br>    }<br><br>    deposit(amount) {<br>        if (amount > 0) {<br>            this.#balance += amount;<br>        } else {<br>            console.log("Invalid deposit amount");<br>        }<br>    }<br>}<br><br>const account = new BankAccount(1000);<br>console.log(account.getBalance()); // 1000<br>account.deposit(500);<br>console.log(account.getBalance()); // 1500<br>``` | ```java<br>class BankAccount {<br>    private double balance;<br><br>    public BankAccount(double initialBalance) {<br>        balance = initialBalance;<br>    }<br><br>    public double getBalance() {<br>        return balance;<br>    }<br><br>    public void deposit(double amount) {<br>        if (amount > 0) {<br>            balance += amount;<br>        } else {<br>            System.out.println("Invalid deposit amount");<br>        }<br>    }<br>}<br><br>public class Main {<br>    public static void main(String[] args) {<br>        BankAccount account = new BankAccount(1000);<br>        System.out.println(account.getBalance()); // 1000<br>        account.deposit(500);<br>        System.out.println(account.getBalance()); // 1500<br>    }<br>}<br>``` |

---

## 6. Key Points

| Feature | JavaScript | Java |
|---------|------------|------|
| **Private Fields** | Yes (`#fieldName`) since ES2022 | Yes (`private` modifier) |
| **Access Modifiers** | Not traditional — uses `#` or closures | `public`, `private`, `protected`, default |
| **Getters/Setters** | `get`, `set` keywords or normal methods | Explicit `getX()` / `setX()` methods |
| **Direct Access Restriction** | Runtime error for private fields | Compile-time error for private fields |

---

## 7. Advantages
- Protects sensitive data.
- Reduces accidental data corruption.
- Easier to change internal logic without affecting other code.
- Helps in modular design.

---

## 8. Disadvantages
- Requires more code (getters/setters).
- Can be slightly verbose for small classes.

---

## 9. Summary
Encapsulation is like **putting your valuables in a safe**:
- You decide **who** can open it.
- You provide a **key (methods)** to interact with its contents.
- Outsiders **cannot touch** the contents directly.


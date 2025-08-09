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

**JavaScript Example** 
class BankAccount {
    // Private field (cannot be accessed outside this class)
    #balance;

    constructor(initialBalance) {
        this.#balance = initialBalance;
    }

    // Getter method (read-only access)
    getBalance() {
        return this.#balance;
    }

    // Setter method (controlled write access)
    deposit(amount) {
        if (amount > 0) {
            this.#balance += amount;
            console.log(`Deposited: ${amount}`);
        } else {
            console.log("Invalid deposit amount");
        }
    }

    withdraw(amount) {
        if (amount > 0 && amount <= this.#balance) {
            this.#balance -= amount;
            console.log(`Withdrawn: ${amount}`);
        } else {
            console.log("Invalid withdrawal amount");
        }
    }
}

// Usage
const account = new BankAccount(1000);

console.log(account.getBalance()); // 1000
account.deposit(500);              // Deposited: 500
console.log(account.getBalance()); // 1500
account.withdraw(200);             // Withdrawn: 200
console.log(account.getBalance()); // 1300

// Direct access will throw an error
// console.log(account.#balance); ❌ SyntaxError: Private field
|

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


# SOLID Principles and Design Patterns in the Pizza Restaurant System

This document explains how the design patterns used in the Pizza Restaurant System align with SOLID principles.

---

## **1. Single Responsibility Principle (SRP)**

**Explanation**:
Each class has a single responsibility. For example:
- `PizzaFactory` is responsible for creating pizzas.
- `InventoryManager` handles inventory management.
- Topping decorators (`Cheese`, `Olives`, etc.) modify pizza attributes.

**Benefit**:
This makes the system modular and easier to maintain.

---

## **2. Open/Closed Principle (OCP)**

**Explanation**:
The system is open for extension but closed for modification. For example:
- New toppings can be added by creating additional decorators (e.g., `ExtraSauce`) without modifying the existing classes.
- New payment methods can be added by implementing the `PaymentMethod` interface.

**Benefit**:
This improves the system's extensibility without risking bugs in existing code.

---

## **3. Liskov Substitution Principle (LSP)**

**Explanation**:
Subclasses can replace their base classes without altering the correctness of the program. For example:
- `Margherita` and `Pepperoni` can replace the base `Pizza` class.
- `Cheese`, `Olives`, and `Mushrooms` replace the base `ToppingDecorator`.

**Benefit**:
This ensures consistency and reliability when extending functionality.

---

## **4. Interface Segregation Principle (ISP)**

**Explanation**:
The `PaymentMethod` interface ensures that payment methods like `Vodafone_Cash` and `CreditCard` only implement relevant methods.

**Benefit**:
This avoids forcing classes to implement unused methods and keeps the interface clean.

---

## **5. Dependency Inversion Principle (DIP)**

**Explanation**:
High-level modules (`main` function) do not depend on low-level modules (`PaymentMethod` implementations). Instead, both depend on abstractions.

**Benefit**:
This promotes decoupling between high-level logic and low-level implementations, improving flexibility and testability.

---

## Conclusion

The application of SOLID principles through design patterns improves the maintainability, scalability, and flexibility of the Pizza Restaurant System.

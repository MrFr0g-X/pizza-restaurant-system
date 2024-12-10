# **Design Patterns in the Pizza Restaurant System**

This document explains the design patterns applied in the Pizza Restaurant System, their benefits, and potential overengineering risks.

---

## **1. Singleton Pattern: Inventory Manager**

### **Description**:
The Singleton Pattern ensures that only one instance of the `InventoryManager` class exists throughout the application. This is essential to manage the shared inventory of ingredients (like Cheese, Olives, and Mushrooms).

### **Benefits**:
- Prevents multiple instances from conflicting when accessing or updating inventory.
- Centralized management of the inventory ensures consistency.

### **Code Example**:
```python
class InventoryManager:
    _inventory = {
        "Margherita": 10,
        "Pepperoni": 10,
        "Cheese": 15,
        "Olives": 10,
        "Mushrooms": 12,
    }

    def check_and_decrement(self, item: str) -> bool:
        if self._inventory.get(item, 0) > 0:
            self._inventory[item] -= 1
            return True
        return False

    def get_inventory(self):
        return self._inventory
```

---

## **2. Factory Pattern: Pizza Factory**

### **Description**:
The Factory Pattern is used to create objects of specific pizza types (`Margherita` and `Pepperoni`). This separates the object creation logic from the main program.

### **Benefits**:
- Simplifies object creation by encapsulating it in a factory class.
- Makes it easy to add new pizza types without modifying existing code.

### **Code Example**:
```python
class PizzaFactory:
    @staticmethod
    def create_pizza(pizza_type):
        if pizza_type == "Margherita":
            return Margherita()
        elif pizza_type == "Pepperoni":
            return Pepperoni()
        else:
            raise ValueError("Invalid pizza type")
```

---

## **3. Decorator Pattern: Toppings**

### **Description**:
The Decorator Pattern allows dynamic addition of toppings to a pizza. Topping decorators like `Cheese`, `Olives`, and `Mushrooms` extend the functionality of a pizza object without modifying its structure.

### **Benefits**:
- Avoids modifying the base pizza classes.
- Provides flexibility to add any combination of toppings during runtime.

### **Code Example**:
```python
class Cheese(ToppingDecorator):
    def get_description(self):
        return f"{self.pizza.get_description()}, Cheese"

    def get_cost(self):
        return self.pizza.get_cost() + 1.0
```

---

## **4. Strategy Pattern: Payment Methods**

### **Description**:
The Strategy Pattern is used to implement different payment methods (`Vodafone_Cash` and `CreditCard`). Each payment method follows the same interface but implements its own logic.

### **Benefits**:
- Simplifies payment processing logic by separating it into different strategies.
- Allows easy addition of new payment methods without modifying existing code.

### **Code Example**:
```python
class PaymentMethod(ABC):
    @abstractmethod
    def pay(self, amount):
        pass

class Vodafone_Cash(PaymentMethod):
    def pay(self, amount):
        print(f"Paid ${amount:.2f} using Vodafone Cash.")
```

---

## **Overengineering Discussion**

### **Definition**:
Overengineering refers to adding unnecessary complexity to a project by implementing features or designs that are not required.

### **Example in This System**:
Adding multiple payment gateways like `PayPal` and `Stripe` when only `Vodafone_Cash` and `CreditCard` are required.

### **Code Example**:
```python
class PayPal(PaymentMethod):
    def pay(self, amount):
        # Complex logic for PayPal payment
```

### **Risks**:
- Increased development time.
- Reduced performance due to unnecessary features.
- Higher maintenance cost.

### **How to Avoid**:
- Focus on the requirements of the system.
- Avoid implementing features that are not requested or essential.

---

## **Conclusion**

The Pizza Restaurant System applies several design patterns to improve flexibility, maintainability, and scalability. While the patterns enhance the system, care must be taken to avoid overengineering by focusing on the requirements and keeping the implementation simple.
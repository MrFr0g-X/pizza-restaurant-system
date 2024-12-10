# **Pizza Restaurant System**

## **Overview**
The Pizza Restaurant System is a simulation of a pizza ordering system implemented in Python using multiple design patterns. The system has been designed and implemented in a Jupyter Notebook, `Pizza_Restaurant_System.ipynb`, for easy readability and interactive execution.

This system applies best practices such as the Singleton, Factory, Decorator, and Strategy patterns to ensure modularity, maintainability, and scalability. It adheres to SOLID principles while avoiding overengineering.

---

## **Features**
1. **Base Pizzas**:
   - Margherita ($5.0)
   - Pepperoni ($6.0)
2. **Toppings**:
   - Cheese ($1.0)
   - Olives ($0.5)
   - Mushrooms ($0.7)
3. **Dynamic Topping Addition**:
   - Customize pizzas by adding one or more toppings.
4. **Inventory Management**:
   - Tracks the availability of pizzas and toppings.
5. **Payment Methods**:
   - Pay using Vodafone Cash or Credit Card.
6. **Cost Calculation**:
   - Calculates and displays the total cost of the order.
7. **Order Details**:
   - Provides a description of the final pizza with toppings and payment confirmation.

---

## **Design Patterns Used**
1. **Singleton Pattern**:
   - Used for inventory management to ensure only one inventory manager instance exists.
2. **Factory Pattern**:
   - Simplifies the creation of pizzas by encapsulating the logic in a factory.
3. **Decorator Pattern**:
   - Allows dynamic addition of toppings to pizzas without modifying the base pizza classes.
4. **Strategy Pattern**:
   - Implements different payment methods with a common interface.

For detailed explanations, refer to the **DesignPatterns.md** file.

---

## **Requirements**
- Python 3.7 or higher
- Jupyter Notebook (Install via `pip install notebook`)

---

## **Setup and Usage**

### **1. Clone the Repository**
```bash
git clone https://github.com/MrFr0g-X/pizza-restaurant-system.git
cd pizza-restaurant-system
```

### **2. Open the Jupyter Notebook**
Launch the Jupyter Notebook server:
```bash
jupyter notebook
```
In the browser, navigate to and open `Pizza_Restaurant_System.ipynb`.

### **3. Interact with the System**
Execute the cells in the notebook sequentially to:
- Select a base pizza.
- Add toppings.
- Choose a payment method.
- View the final order details and inventory status.

---

## **File Structure**
```
.
├── DesignPatterns.md               # Detailed explanation of design patterns
├── SOLID_DP.md                     # Mapping of SOLID principles to the design patterns
├── Pizza_Restaurant_System.ipynb   # Jupyter Notebook implementation
├── README.md                       # Documentation for the project
```

---

## **Example Usage**

### **1. Selecting a Base Pizza**
```text
Welcome to the Pizza Restaurant!
Choose your base pizza:
1. Margherita ($5.0)
2. Pepperoni ($6.0)
0 => to exit
```

### **2. Adding Toppings**
```text
Available toppings:
1. Cheese ($1.0)
2. Olives ($0.5)
3. Mushrooms ($0.7)
4. Finish order
```

### **3. Payment**
```text
Choose payment method:
1. Vodafone Cash
2. Credit Card
```

### **4. Final Order**
```text
Your order:
Description: Pepperoni Pizza, Cheese, Mushrooms
Total cost: $7.70

Paid $7.70 using Vodafone Cash.
```

---

## **Documentation**
- **[DesignPatterns.md](DesignPatterns.md)**: Detailed explanation of the design patterns applied in the system.
- **[SOLID_DP.md](SOLID_DP.md)**: How the design patterns align with SOLID principles.

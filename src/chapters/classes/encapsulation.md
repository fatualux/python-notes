# Encapsulation

Encapsulation is an OOP concept that involves bundling data (attributes) and methods (functions) that operate on the data into a single unit or class. It restricts direct access to some of an object's components, which can help prevent accidental interference and misuse.

### Principles of Encapsulation

1. **Private Attributes and Methods**: By marking attributes and methods as private, you restrict their access from outside the class. This is done by prefixing the attribute or method name with an underscore (`_`) or double underscore (`__`).

   ```python
   class Car:
       def __init__(self, make, model):
           self._make = make  # Protected attribute
           self.__model = model  # Private attribute

       def get_model(self):
           return self.__model

       def set_model(self, model):
           self.__model = model

   my_car = Car("Toyota", "Corolla")
   print(my_car.get_model())  # Output: Corolla
   # print(my_car.__model)  # Raises AttributeError
   ```

2. **Public Methods**: Public methods provide controlled access to the private attributes. They are used to get or set the values of private attributes, thereby providing an interface to interact with the data in a controlled manner.

   ```python
   class Account:
       def __init__(self, balance):
           self.__balance = balance

       def deposit(self, amount):
           if amount > 0:
               self.__balance += amount

       def withdraw(self, amount):
           if 0 < amount <= self.__balance:
               self.__balance -= amount

       def get_balance(self):
           return self.__balance

   my_account = Account(100)
   my_account.deposit(50)
   print(my_account.get_balance())  # Output: 150
   my_account.withdraw(30)
   print(my_account.get_balance())  # Output: 120
   ```

### Benefits of Encapsulation

- **Control**: Encapsulation allows control over how the data in a class is accessed and modified, ensuring that the data is used in a consistent and predictable manner.
- **Flexibility and Maintenance**: It provides the ability to change the internal implementation of the class without affecting the external code that uses the class.
- **Increased Security**: Protects the internal state of the object from unintended or harmful changes by restricting access to private attributes and methods.


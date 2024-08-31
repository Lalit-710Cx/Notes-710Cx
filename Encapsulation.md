---
date: 2024-08-31T02:23:00
tags:
  - python/oopsConcept
  - python
wikilinks: "[[Reference_Variable]]"
---

Encapsulation is the way to hide the data in a Class.
It's represent in the manner of `__data`
 Example:
 ```python
class Atm:

    def __init__(self):
        self.__pin = None
        self.__balance = 0
        self.__menu()

    def get_pin(self):
        return self.__pin

    def get_balance(self):
        return self.__balance

    def set_pin(self, new_pin):
        if isinstance(new_pin, str):
            self.__pin = new_pin

    def set_balance(self, new_balance):
        if isinstance(new_balance, int):
            self.__balance = new_balance


```

here we are using the encapsulation method
 ##### note:
 `There is no Private class in Python`
 you have private a data type than that can save as the `_classname__datatype`
## Getter method📲:
__from out side of the Class we can access the the data type using getter method  😄
-->it return the value of that data__
```python
    def get_pin(self):
        return self.__pin

    def get_balance(self):
        return self.__balance
```

## Setter method 📵:
__from the outside of the class we can modify the data type using the setter method__ 
```python
    def set_pin(self, new_pin):
        if isinstance(new_pin, str):
            self.__pin = new_pin

    def set_balance(self, new_balance):
        if isinstance(new_balance, int):
            self.__balance = new_balance
```

## Code of conduct:
```python
class Atm:

    def __init__(self):
        self.__pin = None
        self.__balance = 0
        self.__menu()

    def get_pin(self):
        return self.__pin

    def get_balance(self):
        return self.__balance

    def set_pin(self, new_pin):
        if isinstance(new_pin, str):
            self.__pin = new_pin

    def set_balance(self, new_balance):
        if isinstance(new_balance, int):
            self.__balance = new_balance

    def __menu(self):
        while True:
            user_input = input("""
                What would you like to do?
                1. Enter 1 to create pin
                2. Enter 2 to deposit
                3. Enter 3 to withdraw
                4. Enter 4 to check balance
                5. Enter 5 to exit
            """)

            if user_input == "1":
                self.create_pin()
            elif user_input == "2":
                self.deposit()
            elif user_input == "3":
                self.withdraw()
            elif user_input == "4":
                self.check_balance()
            elif user_input == "5":
                print("Goodbye!")
                break
            else:
                print("Invalid choice. Please try again.")

    def create_pin(self):
        if self.__pin is None:
            self.__pin = input("Enter the pin: ")
            print("Pin is registered")
        else:
            print("Pin is not registered")

    def deposit(self):
        temp = input("Enter the Pin: ")
        if temp == self.__pin:
            try:
                amount = int(input("Enter the deposite amount: "))
                self.__balance += amount
                print(f"deposite{amount}, total balance{self.__balance}")
            except ValueError:
                print("Invalid amount. Please enter a valid integer.")
        else:
            print("Incurract Pin")

    def withdraw(self):
        temp = input("Enter the pin: ")
        if temp == self.__pin:
            amount = int(input("Enter the amount: "))
            if amount <= self.__balance:
                self.__balance -= amount
                print(f"withdraw amount:{amount}, your balance is {self.__balance}")
            else:
                print("You have unsufficient amount in your account")
        else:
            print("Incurrect Pin")

    def check_balance(self):
        print(f"your courrent balance is {self.__balance}")


if __name__ == "__main__":
    atm = Atm()
```
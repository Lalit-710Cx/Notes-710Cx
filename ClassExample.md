---
date: 2024-08-30T02:30:00
tags:
  - python/oopsConcept
  - python
---

if you want to lean class you are access this link [[object]]


```python
class Atm:

    # Constructor
    def __init__(self):
        self.pin = None
        self.balance = 0
        self.menu()

    def create_pin(self):
        if self.pin is None:
            self.pin = input("Enter the pin: ")
            print("Pin is registered successfully.")
        else:
            print("no pin is registered")

    def menu(self):
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

    def deposit(self):
        temp = input("Enter the pin:")
        if self.pin == temp:
            amount = float(input("Enter amount to deposit: "))
            self.balance += amount
            print(f"Deposited {amount}. Current balance: {self.balance}")

    def withdraw(self):
        temp = input("Enter the pin: ")
        if self.pin == temp:
            amount = float(input("Enter amount to withdraw: "))
            if amount <= self.balance:
                self.balance -= amount
                print(f"Withdrew {amount}. Remaining balance: {self.balance}")
            else:
                print("Insufficient funds.")

    def check_balance(self):
        print(f"Current balance: {self.balance}")


atm = Atm()  
```

## Constructor:
Constructor is a special method when it automatic executed  during object create 🍮
```python
	def __init__(self):
		self.pin = ""
		self.balance = 0
		self.menu()
```

## Self:
Class create with `data` and `methods`
In a Class we can't access one method to another method ❎
So, we can do through the `self` method.
self is basically current object to access *the one method to another method*
![[const.png]]

Lets next learn Fraction [[fraction]]
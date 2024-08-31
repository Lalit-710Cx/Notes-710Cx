---
tags:
  - python/oopsConcept
  - python
---

#### Wiki Link: [[Encapsulation]]

# fraction
python can't understand fraction so it will use special method 

```python
class fraction:
    def __init__(self, n, d):
        self.num = n
        self.den = d

    def __str__(self):
        return "{}/{}".format(self.num, self.den)

    def __add__(self, other):
        temp_num = self.num * other.den + self.num * other.den
        temp_den = self.den * self.den

        return "{}/{}".format(temp_num, temp_den)

    def __sub__(self, other):
        temp_num = self.num * other.den - other.num * self.den
        temp_den = self.den * self.den

        return "{}/{}".format(temp_num, temp_den)

    def __mul__(self, other):
        temp_num = self.num * other.den
        temp_den = self.den * other.den

        return "{}/{}".format(temp_num, temp_den)

    def __truevid__(self, other):
        if other.num == 0:
            raise ZeroDivisionError("Not devided by zero")
        else:
            temp_num = self.num * other.den
            temp_den = self.den * other.num
        return "{}/{}".format(temp_num, temp_den)


x = fraction(3, 4)

y = fraction(5, 6)

print(x + y)

print(x - y)

print(x * y)
```

## `__str__`
it is mainly used for the the Displaying simple information about objects in a human-readable format.
-> like fraction have an memory address so that was unreadable so `__str__` method help it to represent it in string format
```python
def __str__(self):
    return f"{self.name} is {self.age} years old"
```

## `__ADD__`
The `__add__` method is called when the addition operator (`+`) is used with instances of your custom class. It should take two arguments: `self` and `other`. This method should return a new object representing the result of the addition, leaving the original objects unchanged

## `__MUL__`
same as add......

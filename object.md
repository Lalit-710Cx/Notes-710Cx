---
date: 2024-08-30T02:30:00
tags:
  - python/oopsConcept
  - python
---
# Objects

`class` is a blue print of object 🪨
in a class 2 things present 
- `Data or property`
- `Function or behavior`
- Class should be in *pascal case* like `ThisIsPascleCase`
- 🌤*small Case* -> `thisIsSmallCase`
- 🐍*snake Case* -> `snake_case`

😄Example:
```python
class Car:
	color="blue" #data
	model="sport" #data
	def calculatorAvgSpeed(km,time):
		#Some code
```

## Object
i can create object something like that:
```python
wagenr = Car()
cricket = Sport()
langoor = Animal()
```

## Object Literal:
```python
>>> L = namedtuple('literal', 'name age')(name='John Smith', age=23)
>>> L
literal(name='John Smith', age=23)
>>> L.name
'John Smith'
>>> L.age
23
```

## Magic method:
In python 🐍 we `__init__` called as a magic method.
there is another more magic method present like
`__main__, __str__, __bool__, __class__, __dir__`
1. automatically called, it not depend on object
2. it is predefined method.
3. every method has its own work.


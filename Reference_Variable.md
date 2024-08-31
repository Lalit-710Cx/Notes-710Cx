---
tags:
  - python
  - python/oopsConcept
date: 2024-08-30T02:52:00
wikilinks: "[[PassByReference]]"
---
# Reference Variables ✍\
```python
sbi = Atm()
```
`Atm()` is the main object but it does not store the address.
like....`<xyz.Atm.object at 0x003245432D8>` it shown the address but did not store the address of the object so we have to create object using Reference variable.
`sbi = Atm()` -> reference variable
## Comparing References:
```python
a = [1, 2, 3]
b = [1, 2, 3]
print(a == b)  # Output: True
print(a is b)  # Output: False

# Check if an object is mutable
def is_mutable(obj):
    return hasattr(obj, '__dict__') or isinstance(obj, (list, dict))

print(is_mutable(a))  # Output: True
print(is_mutable(b))  # Output: True
```

the `is` operator checks if two variables reference the same object in memory.
### Best Practices

1. Understand that variables are references to objects, not pointers to memory addresses.
2. Be aware of the difference between mutable and immutable types.
3. When working with mutable objects, be cautious about unintended side effects.
4. Use the `id()` function to check if two variables reference the same object.

By understanding how reference variables work in Python, you can avoid common pitfalls related to object modification and memory management.

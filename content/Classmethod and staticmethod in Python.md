# Classmethod and staticmethod in Python
#python #code #datastructure

- `classmethod` decorator modify a method which make it being possibly called directly by the class
  - We don't use `self` argument here, we use `cls` passing the class
- We can use `classmethod` to build alternative constructors
```python
@classmethod  # (1)
def frombytes(cls, octets):  # (2)
    typecode = chr(octets[0])  # (3)
    memv = memoryview(octets[1:]).cast(typecode)  # (4)
    return cls(*memv)  # (5)
```

- `staticmehtod` modify the method to not receive any special argument
  - The method acts as simple function

```python

>>> class Demo:
...     @classmethod
...     def klassmeth(*args):
...         return args  # (1)
...     @staticmethod
...     def statmeth(*args):
...         return args  # (2)
...
>>> Demo.klassmeth()  # (3)
(<class '__main__.Demo'>,)
>>> Demo.klassmeth('spam')
(<class '__main__.Demo'>, 'spam')
>>> Demo.statmeth()   # (4)
()
>>> Demo.statmeth('spam')
('spam',)

```

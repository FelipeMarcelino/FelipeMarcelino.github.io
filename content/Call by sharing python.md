# Call by sharing python
#python #memory #python #code

- Mutable parameter changes
- Immutable remains the same
- Function does not change the object identity
- Receives the copy of reference on the arguments

## Code

```python
>>> def f(a, b):
...     a += b
...     return a
...
>>> x = 1
>>> y = 2
>>> f(x, y)
3
>>> x, y  (1)
(1, 2)
>>> a = [1, 2]
>>> b = [3, 4]
>>> f(a, b)
[1, 2, 3, 4]
>>> a, b  (2)
([1, 2, 3, 4], [3, 4])
>>> t = (10, 20)
>>> u = (30, 40)
>>> f(t, u)  (3)
(10, 20, 30, 40)
>>> t, u
((10, 20), (30, 40))
```

## Mutable as default (Source of bug)

- Use the same object as reference for all other objects
```python
class HauntedBus:
    """A bus model haunted by ghost passengers"""

    def __init__(self, passengers=[]):  # (1)
        self.passengers = passengers  # (2)

    def pick(self, name):
        self.passengers.append(name)  # (3)

    def drop(self, name):
        self.passengers.remove(name)

>>> bus1 = HauntedBus(['Alice', 'Bill'])
>>> bus1.passengers
['Alice', 'Bill']
>>> bus1.pick('Charlie')
>>> bus1.drop('Alice')
>>> bus1.passengers
['Bill', 'Charlie']
>>> bus2 = HauntedBus()
>>> bus2.pick('Carrie')
>>> bus2.passengers
['Carrie']
>>> bus3 = HauntedBus()
>>> bus3.passengers
['Carrie']
>>> bus3.pick('Dave')
>>> bus2.passengers
['Carrie', 'Dave']
>>> bus2.passengers is bus3.passengers
True
>>> bus1.passengers
['Bill', 'Charlie']
```
- Correct way to use it:
```python
class TwilightBus:
    """A bus model that makes passengers vanish"""

    def __init__(self, passengers=None):
        if passengers is None:
            self.passengers = []
        else:
            self.passengers = list(passengers)

    def pick(self, name):
        self.passengers.append(name)

    def drop(self, name):
        self.passengers.remove(name)
```
- Safe to modify passsengers inside the `TwilightBus` and also receive immutable types like tuples

### Sources
- Python Fluent - Luciano Ramalho - Second Edition - 2023 - Web Edition
- [[2025-06-09]]

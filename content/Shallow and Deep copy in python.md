# Shallow and Deep copy in python
#python #code #performance #memory

- Shallow copy fills copy using the reference of the object using the same items from the original
  container
  - Example for list: `l2 = list(l1)` or `l2 = l1[:]`
  - Using `copy`
- Deep copy does not share the references, they copy the whole object
  - Using `deepcopy`

```python
class Bus:

    def __init__(self, passengers=None):
        if passengers is None:
            self.passengers = []
        else:
            self.passengers = list(passengers)

    def pick(self, name):
        self.passengers.append(name)

    def drop(self, name):
        self.passengers.remove(name)

>>> import copy
>>> bus1 = Bus(['Alice', 'Bill', 'Claire', 'David'])
>>> bus2 = copy.copy(bus1)
>>> bus3 = copy.deepcopy(bus1)
>>> id(bus1), id(bus2), id(bus3)
(4301498296, 4301499416, 4301499752)
>>> bus1.drop('Bill')
>>> bus2.passengers
['Alice', 'Claire', 'David']
>>> id(bus1.passengers), id(bus2.passengers), id(bus3.passengers)
(4302658568, 4302658568, 4302657800)
>>> bus3.passengers
['Alice', 'Bill', 'Claire', 'David'A]
```

### sources

- Fluent Python - Luciano Ramalho - 2023 - Second Edition - Web Edition
- [[2025-06-09]]

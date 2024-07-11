# Shallow and Deep Copy
#python #programming #comparison #howtocopy

- Python uses `shallow` copy as **default**
- `l2 = list(l1)` creates a shallow copy and `l2 = l1[:]` as well.
- It is possible to implement copy functions with `__copy__` and `__deepcopy__`

```python
>>> l1 = [3, [66, 55, 44], (7, 8, 9)]
>>> l2 = list(l1)
>>> l1.append(100)
>>> l1[1].remove(55)
>>> print('l1:', l1)
>>> print('l2:', l2)
l1: [3, [66, 44], (7, 8, 9), 100]
l2: [3, [66, 44], (7, 8, 9)]
>>> l2[1] += [33, 22]
>>> l2[2] += (10, 11)
>>> print('l1:', l1)
>>> print('l2:', l2)
l1: [3, [66, 44, 33, 22], (7, 8, 9), 100]
l2: [3, [66, 44, 33, 22], (7, 8, 9, 10, 11)]
# They point to the same list yet but with some modifications
# The immutable object tuple does not change inside the mutable one
# List on the l1[1] is the only object which is mutable that change in both object
```

- An example with deep copy:

```python
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
['Alice', 'Bill', 'Claire', 'David']
```

### References
Ramalho, 2022, 208-213

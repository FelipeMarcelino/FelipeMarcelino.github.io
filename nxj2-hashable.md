# Hashable
#python #programming #datastructure #language

- An object is `hashable` when it has the methods `__eq__` and `__hash__` implemented.
- Types defined by user are `hashable` if they attribute never change during it existence/life.
- `Strings`, `Bytes` and `Numbers` are all hashable.
- Containers, like [[82os-python-tuples]], are `hashable` if they `imutable` and its objects are `hashable` as well.

### References
Ramalho, 2022, 83-96

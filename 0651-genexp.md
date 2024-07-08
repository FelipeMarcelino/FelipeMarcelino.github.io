# genexp
#programming #language #python #functional

- Save more memory comparable to [[ndtq-listcomp]]
- Can be used with [[82os-python-tuples]], arrays and other sequences
- Save the cost to build a [[aw9b-python-list]]
- The result can be saved as list, tuple, or dictionary

```python
>>> symbols
>>> tuple (ord(symbol) for symbol in symbols)
(36, 162, 163, 165, 8364, 164)

>>> import array
>>> array.array ('I', (ord(symbol) for symbol in symbols))

```
- https://medium.com/dsc-ghrce/python-list-comprehension-vs-generator-expression-db1a66dc7e69

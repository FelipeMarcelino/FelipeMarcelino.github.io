# genexp
#programming #language #python #functional

- Save more memory comparable to [[ndtq-listcomp]]
- Can be used with [[82os-python-tuples]], arrays and other sequences
- Save the cost to build a [[aw9b-python-list]]

```python
>>> symbols
>>> tuple (ord(symbol) for symbol in symbols)
(36, 162, 163, 165, 8364, 164)

>>> import array
>>> array.array ('I', (ord(symbol) for symbol in symbols))
array('I', [36, 162, 163, 165, 8364, 1647])

```

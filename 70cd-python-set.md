# Python Set
#python #datastructure #programming #language #efficiency

- They are two types of sets: `set` and `frozenset`
   * `set`: Not hashable, cannot be nested
   * `frozenset`: Hashable, we can have `frozenset` inside `set`
- Take a look on both codes below

```python
found = len(needles & haystack) # (1)

found = 0 # (2)
for n in needless:
	if n in haystack:
		found += 1
```
- The code (1) has superior performance than the code (2).
- To build a set

```python
>>> s = {1} # faster than
>>> s = set([1,2,3])
```
- Take a look on [[n803-setcomp]]#
- Elements inside `set` need to be [[nxj2-hashable]] or has the methods `__hash__` and `__eq__`
   * But the check of existence of element is fast
- Sets have memory overhead
- Sorting is not guaranteed in `set`, adding elements can change the order
- [[9n4u-python-dictionary]] methods like `keys()` and `items()` implement some `set` methods like: **&, |, - and ^.**

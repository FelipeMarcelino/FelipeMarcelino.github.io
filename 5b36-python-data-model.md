# Python Data Model
#programming #language #python #datastructure

Data model is a description or interface for Python as framework.
It makes you code easy to interpret and being supported by common functions/methods in python
For example if you implement the method ```__get_item__``` you are able to use the following methods on python
- `choice`
- `slice [:3]`
- `index [1]`
- `iteration`

```python
# iteration
for obj in objs:
    print(obj)
```

Python has other methods like `__repr__` to represent the object like as the creation of this. `__bool__` to
make conditional valid or invalid in some situation. `__str__` to present/print the object in human-readable way and
others.

**Obs**: It is common to use `!r` with the function `__repr__` and *f-strings*.

In data models the functions is not call by the use but by the interpreter, in that way, the code has more performance.
The only method call by the user is the method to initialize the object/class `__init__`.

An example of python data model.

```python
import collections

Card = collections.namedtuple('Card', ['rank', 'suit'])

class FrenchDeck:
	ranks = [str(n) for n in range(2, 11) + list('JQKA')]
	suits = 'spades diamonds clubs hears'.split()

	def __init__(self):
		self._cards = [Card(rank, suit) for suit in self.suits
						for rank in self.ranks]

	def __len__(self):
		return len(self._cards)

	def __get__item(self, position):
		return self._cards[position]
```

Implementing python data model it is possible above is possible to use it in the iteration `for` or
[[aw9b-python-list]].
Avoid [[82os-python-tuples]] for mutable objects.

### References
Ramanlho, 2022, Chapter 1

# collections.namedtuple
#python #programming #storage #data #datastructure #class

- They are factory of subclasses of`tuple` with simple method implementation
- `__eq__` method compare `id` when not implemented
- `__repr__` is implemented on the class
- It is immutable

```python
>>> from collections import namedtuple
>>> Coordinate = namedtuple('Coordinate', 'lat lon')
>>> issubclass(Coordinate, tuple)
True
>>> moscow = Coordinate(55.756, 37.617)
>>> moscow
Coordinate(lat=55.756, lon=37.617)
>>> moscow == Coordinate(lat=55.756, lon=37.617)
True
```

- Some methods:
	- `_fields`: give the attributes of the classes
	- `_make(iterable)`: create the instance from a iterable
	- `_asdict`: return a dictionary, common for JSON serialization

```python
>>> City._fields
('name', 'country', 'population', 'location')
>>> Coordinate = namedtuple('Coordinate', 'lat lon')
>>> delhi_data = ('Delhi NCR', 'IN', 21.935, Coordinate(28.613889, 77.208889))
>>> delhi = City._make(delhi_data)
>>> delhi._asdict()
{'name': 'Delhi NCR', 'country': 'IN', 'population': 21.935,
'location': Coordinate(lat=28.613889, lon=77.208889)}
>>> import json
>>> json.dumps(delhi._asdict())
'{"name": "Delhi NCR", "country": "IN", "population": 21.935,
"location": [28.613889, 77.208889]}'

>>> Coordinate = namedtuple('Coordinate', 'lat lon reference', defaults=['WGS84']) # Here the rightmost receive the default values
>>> Coordinate(0, 0)
Coordinate(lat=0, lon=0, reference='WGS84')
>>> Coordinate._field_defaults
{'reference': 'WGS84'}
```

- To inject method you need to create a variable and put your method there

```python
>>> Card.suit_values = dict(spades=3, hearts=2, diamonds=1, clubs=0)
>>> def spades_high(card):
...     rank_value = FrenchDeck.ranks.index(card.rank)
...     suit_value = card.suit_values[card.suit]
...     return rank_value * len(card.suit_values) + suit_value
>>> Card.overall_rank = spades_high
>>> lowest_card = Card('2', 'clubs')
>>> highest_card = Card('A', 'spades')
>>> lowest_card.overall_rank()
0
>>> highest_card.overall_rank()
51
```

### References
- Ramalho, 2022, p164-172

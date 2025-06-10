# Dataclass, collections.namedtuple and typing.NamedTuple
#datasctructure #python #code

- They have already implemented special methods `__init__`, `__repr__` and `__eq__`
- `@dataclass` use decorators to activate its function
- `collections.namedtuple` use position arguments to initialize it and its arguments can be passed as iterative string
- `typing.NamedTuple` has the special method `__annotations__` to store annotations. However,
python ignores its in the execution time
- `@dataclass` parameters like `frozen` and `unsafe_hash` are `False` per default.
- We can use it with [[Pattern Matching in Python ]]
    - For named classes and positioned classes arguments

### `__post_init__`

- `@dataclass` has the special method `__post_init__`
- This special method open space to manipulate variables post initializations

```python
@dataclass
class HackerClubMember(ClubMember):
    all_handles = set()
    handle: str = ''

    def __post_init__(self):
        cls = self.__class__
        if self.handle == '':
            self.handle = self.name.split()[0]
        if self.handle in cls.all_handles:
            msg = f'handle {self.handle!r} already exists.'
            raise ValueError(msg)
        cls.all_handles.add(self.handle)

```

## Examples

```python

>>> from collections import namedtuple
>>> Coordinate = namedtuple('Coordinate', 'lat lon')
>>> issubclass(Coordinate, tuple)
True
>>> moscow = Coordinate(55.756, 37.617)
>>> moscow
Coordinate(lat=55.756, lon=37.617)  (1)
>>> moscow == Coordinate(lat=55.756, lon=37.617)  (2)
True

>>> import typing
>>> Coordinate = typing.NamedTuple('Coordinate',
...     [('lat', float), ('lon', float)])
>>> issubclass(Coordinate, tuple)
True
>>> typing.get_type_hints(Coordinate)
{'lat': <class 'float'>, 'lon': <class 'float'>

from typing import NamedTuple

class Coordinate(NamedTuple):
    lat: float
    lon: float

    def __str__(self):
        ns = 'N' if self.lat >= 0 else 'S'
        we = 'E' if self.lon >= 0 else 'W'
        return f'{abs(self.lat):.1f}°{ns}, {abs(self.lon):.1f}°{we}'

```

### Sources

- [[2025-06-06]]
- fluent python - luciano ramalho - 2023 - web edition

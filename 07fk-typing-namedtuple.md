# typing.NamedTuple
#python #programming #datastructure #data #storage #class

-
- They are `immutable` because of inheritance of `tuple`
- Class syntax
- Use `inspect.get_annotations(myclass)` to see about field need to be annotated
- Can use `default` values on fields

```python
from typing import NamedTuple
class Coordinate(NamedTuple):
    lat: float
    lon: float
    reference: str = 'WGS84'
```

- How to inspect with `NamedTuple`:

```python
import typing
class DemoNTClass(typing.NamedTuple):
    a: int
    b: float = 1.1
    c = 'spam'

>>> from demo_nt import DemoNTClass
>>> DemoNTClass.__annotations__
{'a': <class 'int'>, 'b': <class 'float'>}
>>> DemoNTClass.a
<_collections._tuplegetter object at 0x101f0f940>
>>> DemoNTClass.b
<_collections._tuplegetter object at 0x101f0f8b0>
>>> DemoNTClass.c
'spam'



```

- C in that case is a class attribute, and not a `field` (instance attribute)
- Parameter `a` is needed here
- `b` have default value, which is `1.1`

### References
- Ramalho, 2022, p172-179
- Ramalho, 2022, p183-187

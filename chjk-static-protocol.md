# Static Protocol
#programming #python #typing #doc #datamodel #datamodel

- They are subtype of **Duck Typing**, therefore it is necessary only to implement the function/operation of the type.
```python
from typing import Protocol, Any
class SupportsLessThan(Protocol):
    def __lt__(self, other: Any) -> bool: ...

#######################################

from collections.abc import Iterable
from typing import TypeVar
from comparable import SupportsLessThan
LT = TypeVar('LT', bound=SupportsLessThan)
def top(series: Iterable[LT], length: int) -> list[LT]:
    ordered = sorted(series, reverse=True)
    return ordered[:length]

#######################################

class Spam:
...     def __init__(self, n): self.n = n
...     def __lt__(self, other): return self.n < other.n
...     def __repr__(self): return f'Spam({self.n})'

[Spam(5), Spam(4), Spam(3), Spam(2), Spam(1)]
>>> sorted(l)

######################################
l = [object() for _ in range(4)]
>>> sorted(l)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: '<' not supported between instances of 'object' and 'object'
```
- The code above need `__lt__` implemented because it uses `sorted` inside the function, so in that way is necessary a
  comparator for it.

### References
- Ramalho, 2022, 286-291

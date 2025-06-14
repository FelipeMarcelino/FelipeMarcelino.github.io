# Static Protocols
#code #python #datastructure

- They specify one or more methods to be implemented
- They are based on the **Duck Typing** - [[Duck Typing and Nominal Typing]]
```python
from typing import Protocol, Any

class SupportsLessThan(Protocol):
    def __lt__(self, other: Any) -> bool: ...

from collections.abc import Iterable
from typing import TypeVar

from comparable import SupportsLessThan

LT = TypeVar('LT', bound=SupportsLessThan)

def top(series: Iterable[LT], length: int) -> list[LT]:
    ordered = sorted(series, reverse=True)
    return ordered[:length]
```

- Example above shows that the bound need to implement the special method `__lt__`

# Typevar: Generic types in python
#code #python

- Typevars are generic types in python
- They can be used to build custom types
- We can use it to restrict to some types or bound it to some limit

```python
from collections.abc import Sequence
from random import shuffle
from typing import TypeVar

T = TypeVar('T')

def sample(population: Sequence[T], size: int) -> list[T]:
    if size < 1:
        raise ValueError('size must be >= 1')
    result = list(population)
    shuffle(result)
    return result[:size]
```

## Restricted typevar

- We put some accepted types into a typevar. For example:
```python
from collections.abc import Iterable
from decimal import Decimal
from fractions import Fraction
from typing import TypeVar

NumberT = TypeVar('NumberT', float, Decimal, Fraction)

def mode(data: Iterable[NumberT]) -> NumberT:
```
- If we want to add some types on it, we can add it by simpling add into typevar, for example a `str`
`NumberT = TypeVar('NumberT', float, Decimal, Fraction, str)`

## Bound typevar

- They put a superior limit on the `typevar`.
```python
from collections import Counter
from collections.abc import Iterable, Hashable
from typing import TypeVar

HashableT = TypeVar('HashableT', bound=Hashable)

def mode(data: Iterable[HashableT]) -> HashableT:
    pairs = Counter(data).most_common(1)
    if len(pairs) == 0:
        raise ValueError('no mode for empty data')
    return pairs[0][0]
```
- The example above means that the `HashableT` accepts any `Hashable` or its subclass

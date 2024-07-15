# Parameterized Generics and TypeVar
#python #typing #doc #programming

- Example `list[T]`, since `T` being a type T chosen or limited by the **bound**
- Use the following syntax: `number = TypeVar('number', float, Decimal, Fraction)` and `del mode(data:
  Iterable[number] -> number)` in that case I can assign `number` to `T`
- Using **bound** to limit the types accepted
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
- Code above states that `Hashable` and its **subtypes** are acceptable
- Special types that accept any strings:
```python
AnyVar = TypeVar(`AnyVar`, bytes, str)
```

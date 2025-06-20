# Type Hints
#python #code

- Type hints are optional
- The type `Any` is used when the type is not assign
- It does not improve performance
- `mypy` is one of the tool used to static check
```
[mypy]
python_version = 3.9
warn_unused_configs = True
disallow_incomplete_defs = True
```

- Below a type hint for a function
    - Use one space after `:` and one space between two sides `=`
```python
def show_count(count: int, singular: str, plural: str = '') -> str:
    if count == 1:
        return f'1 {singular}'
    count_str = str(count) if count else 'no'
    if not plural:
        plural = singular + 's'
    return f'{count_str} {plural}'
```
- We can use `None` as default value for parameter
`def show_count(count: int, singular: str, plural: Optional[str] = None) -> str:`
- Use `Optional` with `None`
- Import types using `from typing import X` to decrease function signs
- Duck Typing and Nominal Typing are two types used in Python
- The type `Any` accepts anything
- General types have interface more restricts, which is, they support less operations. `object`
implements less operations than `abc.Sequence`, which implements implements less operations than
`abc.MutableSequence`, which in turn implement less operations than `list`
- [[Liskov Substitution]]
- `Union` means `or`
    - `Union[str, None]`: means that parameter or variable can be `str` or `None`
- Generic collections: `container[item]` like we have for `list[str]`
- [[Tuple: records and immutable list]] as register/records use types inside `[]`
    - tuple as immutable list use type with `ellipsis` `tuple[int,...]`
- NamedTuple: Works like classes
- dict:
```python
def name_index(start: int = 32, end: int = STOP_CODE) -> dict[str, set[str]]:
    index: dict[str, set[str]] = {}  # (2)
    for char in (chr(i) for i in range(start, end)):
        if name := unicodedata.name(char, ''):  # (3)
            for word in tokenize(name):
                index.setdefault(word, set()).add(char)
    return index
```
- It is better to use to use `abc.MutableMapping` or `abc.Mapping` for type hints
    - `dict` is brother of `UserDict`
- Use `list` for returning and `Iterable` and `Sequence` for parameters
```python
from collections.abc import Iterable

FromTo = tuple[str, str]  # (1)

def zip_replace(text: str, changes: Iterable[FromTo]) -> str:  # (2)
    for from_, to in changes:
        text = text.replace(from_, to)
    return text
```

- [[Typevar: Generic types in python ]]#
- [[Static Protocols]]#

- `Callable` is used to type callable objects
    - `Callable[[ParamType1, ParamType2], ReturnType]`
    - Example: [[Strategy using functions]]

### sources

- fluent python - Luciano Ramalho - 2023 - Second Edition - Web Edition
- [[]]

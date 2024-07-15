# Typing Maps
#python #programming #typing #doc

- [[9n4u-python-dictionary]] typing is simple depending on the key and values: `dict[str, set[str]]`
```python
import sys
import re
import unicodedata
from collections.abc import Iterator
RE_WORD = re.compile(r'\w+')
STOP_CODE = sys.maxunicode + 1
def tokenize(text: str) -> Iterator[str]:
    """return iterable of uppercased words"""
    for match in RE_WORD.finditer(text):
        yield match.group().upper()
def name_index(start: int = 32, end: int = STOP_CODE) -> dict[str, set[str]]:
    index: dict[str, set[str]] = {}
    for char in (chr(i) for i in range(start, end)):
        if name := unicodedata.name(char, ''):
            for word in tokenize(name):
                index.setdefault(word, set()).add(char)
    return index
```
- `UserDict` is not accepted when passing `dict` because the former is not subclass of the latter

### References
- Ramalho, 2022, p276-278

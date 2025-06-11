# Special method __call__
#python #datastructure #code

- Objects in python can be callable as well using the special method `__call__`

```python
class BingoCage:

    def __init__(self, items):
        self._items = list(items)
        random.shuffle(self._items)

    def pick(self):
        try:
            return self._items.pop()
        except IndexError:
            raise LookupError('pick from empty BingoCage')

    def __call__(self):
        return self.pick()

>>> bingo = BingoCage(range(3))
>>> bingo.pick()
1
>>> bingo()
0
>>> callable(bingo)
True
```

- Objects similar to the functions
- Implementation of `decorators` using `__call__`. Decorators need to **invoked**

### Sources

- Fluent Python - Luciano Ramalho - 2023 - Second Edition - Web Edition

# Callable Objects
#python #programming #functions #datamodel

- We have different type of callable objects
	- built-in functions: `len`
	- classes: `__init__`
	- instances: using `__call__`
	- generator: with `yield` keyword
	- user defined functions with `def` and [[ey8t-lambda-function]]
- They are all called with `()`
- How to know if object is callable: `callable()`
- How to type callable objects: [[80tb-typing-callable]]#

```python
import random
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
```

- Code above show an example of `__call__`
	- Good when you want to obtain the state of the object and preserve it state between calls
	- When you implement `decorators`

### References
- Ramalho, 2022, p237-240

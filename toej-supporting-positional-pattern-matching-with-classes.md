# Supporting Positional Pattern Matching with Classes
#python #datamodel #programming #class

- Implement `__match_args__` to indicate which positional pattern to match
- No need to have all public attributes, however the `__init__` are required and in contrast with the optional ones

```python
class Vector2d:
    __match_args__ = ('x', 'y') ## Indicating which positional pattern to have and to match (Use public names)
    # etc...

case Vector2d(0, 0):
	print(f'{v!r} is null')
case Vector2d(0):
	print(f'{v!r} is vertical')
case Vector2d(_, 0):
	print(f'{v!r} is horizontal')
case Vector2d(x, y) if x==y:
	print(f'{v!r} is diagonal')
case _:
	print(f'{v!r} is awesome')
```

### References
- Ramalho, 2022, 377-378

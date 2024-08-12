# __slot__ in Python
#python #programming #efficiency #datamodel #class

- Attributes are stored inside a `dictionary`
- The usage of `__slot__` make them stored into array, saving memory
- Can be a tuple or a list to define the attributes
- **Subclasses** must have defined `__slot__` again to have its benefits.
- `__slot__` make the class impossible to create dynamic attribute
- Use `__weak__` inside `__slot__` for `del` and **Garbage Collector**
- It is not possible to use `@cached_property`
- [[toej-supporting-positional-pattern-matching-with-classes]]

```python
>>> class Pixel:
...     __slots__ = ('x', 'y')
...
>>> p = Pixel()
>>> p.__dict__
Traceback (most recent call last):
  ...
AttributeError: 'Pixel' object has no attribute '__dict__'
>>> p.x = 10
>>> p.y = 20
>>> p.color = 'red'
Traceback (most recent call last):
  ...
AttributeError: 'Pixel' object has no attribute 'color'
```
```python
>>> class OpenPixel(Pixel):
...     pass
...
>>> op = OpenPixel()
>>> op.__dict__
{}
>>> op.x = 8
>>> op.__dict__
{}
>>> op.x
8
>>> op.color = 'green'
>>> op.__dict__
{'color': 'green'}
```
```python
>>> class ColorPixel(Pixel):
...    __slots__ = ('color',)
>>> cp = ColorPixel()
>>> cp.__dict__
Traceback (most recent call last):
  ...
AttributeError: 'ColorPixel' object has no attribute '__dict__'
>>> cp.x = 2
>>> cp.color = 'blue'
>>> cp.flavor = 'banana'
Traceback (most recent call last):
  ...
AttributeError: 'ColorPixel' object has no attribute 'flavor'
```
```python
class Vector2d:
    __match_args__ = ('x', 'y') # List the public names
    __slots__ = ('__x', '__y') # List the privated names
```


### References
- Ramalho, 2022, p384-388

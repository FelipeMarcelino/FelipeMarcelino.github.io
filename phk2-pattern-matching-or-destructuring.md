# Pattern Matching or Destructuring
 #python #programming #datastructure #language

- Destructuring like `Clojure` and `Scala`
- Pattern match are way to `match/case` things like `if/else` conditional.
- For `dict` the `order` of `key` does **not matter** and are possible to have `partial`. Which are different from
  [[4dyw-python-sequences]].

 ```python
 # Dictionary
# tag::DICT_MATCH[]
def get_creators(record: dict) -> list:
    match record:
        case {'type': 'book', 'api': 2, 'authors': [*names]}:  # <1>
            return names
        case {'type': 'book', 'api': 1, 'author': name}:  # <2>
            return [name]
        case {'type': 'book'}:  # <3>
            raise ValueError(f"Invalid 'book' record: {record!r}")
        case {'type': 'movie', 'director': name}:  # <4>
            return [name]
        case _:  # <5>
            raise ValueError(f'Invalid record: {record!r}')
# end::DICT_MATCH[]

>>> b1 = dict(api=1, author='Douglas Hofstadter',
...         type='book', title='Gödel, Escher, Bach')
>>> get_creators(b1)
['Douglas Hofstadter']
>>> from collections import OrderedDict
>>> b2 = OrderedDict(api=2, type='book',
...         title='Python in a Nutshell',
...         authors='Martelli Ravenscroft Holden'.split())
>>> get_creators(b2)
['Martelli', 'Ravenscroft', 'Holden']
>>> get_creators({'type': 'book', 'pages': 770})
Traceback (most recent call last):
    ...
ValueError: Invalid 'book' record: {'type': 'book', 'pages': 770}
>>> get_creators('Spam, spam, spam')
Traceback (most recent call last):
    ...
ValueError: Invalid record: 'Spam, spam, spam'
# end::DICT_MATCH_TEST[]
"""
```

```python
 # Dictionary partial with destructuring
 >>> food = dict (category='ice cream', flavor='vanilla', cost=199)
 >>> match food:
	case {'category': 'ice cream', **details}: # Details capture the rest of the values
		print(f'Ice cream details: {details}')
 ```

 ## Sequence Pattern

 - Sequence pattern => () = []
 - str, bytes = bytearray are treated atomic, they need to be converted into tuple or list
 - The symbol `_` can be used multiple times on the **pattern matching**
 - We can use classes or `str`, `float` or `classes` to runtime check the type of pattern match

```python
case [str(name), _, _, (float(lat), float(lon)), as coord]  lon <= 0 # Runtime check with float and str
```
- The "lon ≤ 0" part is known as **guard rail**. They are evaluated only if match is matched.

```python
case ['define', Symbol as name, value_exp] # Test if name is Symbol
```

```python
metro_areas = [
    ('Tokyo', 'JP', 36.933, (35.689722, 139.691667)),
    ('Delhi NCR', 'IN', 21.935, (28.613889, 77.208889)),
    ('Mexico City', 'MX', 20.142, (19.433333, -99.133333)),
    ('New York-Newark', 'US', 20.104, (40.808611, -74.020386)),
    ('São Paulo', 'BR', 19.649, (-23.547778, -46.635833)),
]

def main():
    print(f'{"":15} | {"latitude":>9} | {"longitude":>9}')
    for record in metro_areas:
        match record:
            case [name, _, _, (lat, lon)] if lon <= 0:
                print(f'{name:15} | {lat:9.4f} | {lon:9.4f}')
main()
 ```

# Special method __format__
#python #code

- `__format__` is used to specify a format to print something
- It has a mini language of format specification
- the `__format__` function can be called using `format()` and `str.format()`
```python
>>> brl = 1 / 4.82  # BRL to USD currency conversion rate
>>> brl
0.20746887966804978
>>> format(brl, '0.4f')  # (1)
'0.2075'
>>> '1 BRL = {rate:0.2f} USD'.format(rate=brl)  # (2)
'1 BRL = 0.21 USD'
>>> f'1 USD = {1 / brl:0.2f} BRL'  # (3)
'1 USD = 4.82 BRL'
```
- After the colon `:` it has the specification of the string

```python
def __format__(self, fmt_spec=''):
        if fmt_spec.endswith('p'):  # (1)
            fmt_spec = fmt_spec[:-1]  # (2)
            coords = (abs(self), self.angle())  # (3)
            outer_fmt = '<{}, {}>'  # (4)
        else:
            coords = self  # (5)
            outer_fmt = '({}, {})'  # (6)
        components = (format(c, fmt_spec) for c in coords)  # (7)
        return outer_fmt.format(*components)  # (8)

>>> format(Vector2d(1, 1), 'p')
'<1.4142135623730951, 0.7853981633974483>'
>>> format(Vector2d(1, 1), '.3ep')
'<1.414e+00, 7.854e-01>'
>>> format(Vector2d(1, 1), '0.5fp')
'<1.41421, 0.78540>'
```

- The code above states a specific format when it ends with `p` using coordinates
  - It applies the formats until `[:-1]`

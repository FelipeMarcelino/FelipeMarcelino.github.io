# format
#datamodel #python #programming

- **f-strings** and `str.format()`
	- Exa: `0.4f`, `0.2f`
- Each of one types, `int` or `float`, support different kind of formats for example
	- `int` can be formatted as base 2 and base 16
	- `float` can be formmated using `fixed-point` and `%` percentage
	- `strftime` is to support `datetime` or dates in general
- There is a **mini-language** for the formatters
	- Avoid the same letter or codes for custom regarding `string`, `int` and `float`
		- You can use `p` for polar coordinates for example

```python
def __format__(self, fmt_spec=''):
        components = (format(c, fmt_spec) for c in self)
        return '({}, {})'.format(*components)
```

```python
 def __format__(self, fmt_spec=''):
        if fmt_spec.endswith('p'):
            fmt_spec = fmt_spec[:-1]
            coords = (abs(self), self.angle())
            outer_fmt = '<{}, {}>'
        else:
            coords = self
            outer_fmt = '({}, {})'
        components = (format(c, fmt_spec) for c in coords)
        return outer_fmt.format(*components)

>>> format(Vector2d(1, 1), 'p')
'<1.4142135623730951, 0.7853981633974483>'
>>> format(Vector2d(1, 1), '.3ep')
'<1.414e+00, 7.854e-01>'
>>> format(Vector2d(1, 1), '0.5fp')
'<1.41421, 0.78540>'
```

### References
- Ramalho, 2022, p370-374

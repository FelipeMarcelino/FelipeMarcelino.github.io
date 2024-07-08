# Dictionary View
#python #efficiency #programming #language

- It is high performance operations on dictionaries
- If the **object** changes the **view** changes as well.
- It is iterable

```python
>>> d = dict(a=10, b=20, c=30)
>>> values = d.values()
>>> values
dict_values([10, 20, 30])
>>> len(values)
3
>>> list(values)
[10, 20, 30]
>>> reversed(values)
<dict_reversevalueiterator object at 0x10e9e7310>
>>> values[0]
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'dict_values' object is not subscriptable
```

### References
- Ramalho, 2033, p101-103

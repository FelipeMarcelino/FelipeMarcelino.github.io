# setcomp
#python #programming #language #efficiency

- Create set like we have for [[x4fp-dictcomp]] and [[ndtq-listcomp]]

```python
>>> from unicodedata import name
>>> {chr(i) for i in range(32, 256) if 'SIGN' in name(chr(i),'')}
{'§', '=', '¢', '#', '¤', '<', '¥', 'µ', '×', '$', '¶', '£', '©',
'°', '+', '÷', '±', '>', '¬', '®', '%'}
```

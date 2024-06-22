# Walrus
#programming #language #python #special:

Walrus operator is a special case of #[[ndtq-listcomp]] when you need to store the last element of the list.
```python
x = 'ABC'
codes = [last := ord(c) for c in x]
# last will be 67
```

# Function as object
#python #code

- Using function inside a variable
- We can use `__doc__` to see function documentation

```python
>>> fact = factorial
>>> fact
<function factorial at 0x...>
>>> fact(5)
120
>>> map(factorial, range(11))
<map object at 0x...>
>>> list(map(factorial, range(11)))
[1, 1, 2, 6, 24, 120, 720, 5040, 40320, 362880, 3628800]
```

### Sources

- Fluent Python - Luciano Ramalho - 2023 - Second Edition - Web Edition

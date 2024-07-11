# High Order Functions
#python #functional #programming

- A function that receive another function or returns a function: Example: `map`, `reduce`, `filter`
- `map` + `filter` = [[ndtq-listcomp]] and [[0651-genexp]] using `if`
- `reduce` = `sum`

```python
>>> fact = factorial # Function is assign to a variable, functioning like object
>>> fact
<function factorial at 0x...>
>>> fact(5)
120
>>> map(factorial, range(11))
<map object at 0x...>
>>> list(map(factorial, range(11))) # receives factorial
[1, 1, 2, 6, 24, 120, 720, 5040, 40320, 362880, 3628800]
>>> fruits = ['strawberry', 'fig', 'apple', 'cherry', 'raspberry', 'banana']
>>> sorted(fruits, key=len) # receives the len function
['fig', 'apple', 'cherry', 'banana', 'raspberry', 'strawberry']
```

- [[ey8t-lambda-function]]#
- [[4fmy-packages-for-functional-programming-in-python]]#
## Partial

- Receives one `callable` and `arguments` with predetermined values

```python
>>> from operator import mul
>>> from functools import partial
>>> triple = partial(mul, 3)
>>> triple(7)
21
>>> list(map(triple, range(1, 10)))
[3, 6, 9, 12, 15, 18, 21, 24, 27]
```

### References
- Ramalho, 2022, p234-236
- Ramalho, 2022, p247-249

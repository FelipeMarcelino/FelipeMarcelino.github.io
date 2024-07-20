# cache, lru-cache, singledispatch
#python #efficiency #decorator #designpattern #programming #overriding

## Cache

- Save call results in a `dict` structure, therefore make the process more fast reusing last results
- It for fast commands, because it can fill all the memory because it is unlimited. Another option is `lru_cache` with
  `max_size`
- They are good options for remote API
- All the arguments of the functions need to be hashables ([[nxj2-hashable]]) because they will be save in a `dict`
```python
import functools

from clockdeco import clock

@functools.cache # stacked decorators works like that cache(clock(fibonnaci))
@clock
def fibonacci(n):
	if n < 2:
			return n
		return fibonacci(n - 2) + fibonacci(n - 1)

if __name__ == '__main__':
    print(fibonacci(6))
```

## lru-cache

- Similar to `cache` but has `typed` and `max_size`
- *least-recently-used*: The old ones that weren't read are eliminated
	- `max_size`: limit the amount of entries
	- `typed`: `typed=true` means that `f(1)` and `f(1.0)` are stored separately

## singledispatch

- Imitate the **overloading** from **Java**
	- A function implementation can vary, and the called version depends on only from the first type parameter
- Use `collections.abc` and `protocols` for the types because they are better for future modification and `virtual
  classes`. In other words, **avoid concrete types**
- [[rugi-singledispatch-implementation]]#

### Reference
- Ramalho, 2022, p320-329

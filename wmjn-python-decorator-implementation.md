# Python Decorator Clock Implementation
#decorator #designpattern #apply #python #programming

```python
def clock(func):
    def clocked(*args):
        t0 = time.perf_counter()
        result = func(*args)
        elapsed = time.perf_counter() - t0
        name = func.__name__
        arg_str = ', '.join(repr(arg) for arg in args)
        print(f'[{elapsed:0.8f}s] {name}({arg_str}) -> {result!r}')
        return result
    return clocked
```

```python
@clock
def factorial(n)
	return if n < 2 else n * factorial(n-1)
```
- The function above becomes: `factorial = clock(factorial)`
	- In other words, the factorial becomes a reference to `clocked` function

```python
>>> import clockdeco_demo
>>> clockdeco_demo.factorial.__name__.'clocked'
```

- The function accept the same arguments but return what the decorator want to return. Make some extra processing with
  the decorator.
- To support `keyword` arguments you have to use `functools.wraps(func)`

```python
def clock(func):
    @functools.wraps(func)
    def clocked(*args, **kwargs):
        t0 = time.perf_counter()
        result = func(*args, **kwargs)
        elapsed = time.perf_counter() - t0
        name = func.__name__
        arg_lst = [repr(arg) for arg in args]
        arg_lst.extend(f'{k}={v!r}' for k, v in kwargs.items())
        arg_str = ', '.join(arg_lst)
        print(f'[{elapsed:0.8f}s] {name}({arg_str}) -> {result!r}')
        return result
    return clocked
```

- There is a version with parameters: [[aswx-python-decorator-implementation-with-parameters]]

### References
- Ramalho, 2022, p317-319

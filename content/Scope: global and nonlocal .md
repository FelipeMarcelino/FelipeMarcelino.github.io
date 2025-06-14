# Scope: global and nonlocal
#python #code

- They are multiple variable scopes: `local`, `global`, `nonlocal`
```python
>>> b = 6
>>> def f3(a):
...     global b
...     print(a)
...     print(b)
...     b = 9
...
>>> f3(3)
3
6
>>> b
9
```
- Code above would have been failed if `global` was not used in the function:
`UnboundLocalError: local variable 'b' referenced before assignment`
- `nonlocal` is used for **free variables**
```python
def make_averager():
    count = 0
    total = 0

    def averager(new_value):
        nonlocal count, total
        count += 1
        total += new_value
        return total / count

    return averager
```

## Closures

```python
def make_averager():
    series = []

    def averager(new_value):
        series.append(new_value)
        total = sum(series)
        return total / len(series)

    return averager

>>> avg = make_averager()
>>> avg(10)
10.0
>>> avg(11)
10.5
>>> avg(15)
12.0
```
- In the example above, `series` is a free variable
- `series` is where we call `closures`
- Closures are functions holding free variables when the function is defined in a way that these variables
can be used late, when the function is invoked but the scope of the definition is not available anymore

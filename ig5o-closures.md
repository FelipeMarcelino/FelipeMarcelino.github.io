# Closures
#python #programming #scope

- Closures uses **Free Variables**
	- They are non-local neither non-global
	- They come from external functions
- They are made using nested functions

```python
def make_averager():
    series = [] # mutable free variable
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

- But when you dealing with immutable variables, a keyword `nonlocal` is necessary to identify the free variables
  outside of local scope
	- When the immutable variable changes, a new variable is created, but local. However, this local variable does not
	  exist.

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

>>> avg = make_averager()
>>> avg(10)
Traceback (most recent call last):
  ...
UnboundLocalError: local variable 'count' referenced before assignment
>>>

def make_averager():
    count = 0
    total = 0
    def averager(new_value):
        nonlocal count, total # Fix the problem above
        count += 1
        total += new_value
        return total / count
    return averager
```

### References
- Ramalho, 2022, p311-314

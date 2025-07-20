# High Order Function in Python
#python #code #datastructure

- High order function are functions that accept other functions
- Example: `sorted` and `map`

```python
>>> def reverse(word):
...     return word[::-1]
>>> reverse('testing')
'gnitset'
>>> sorted(fruits, key=reverse)
['banana', 'apple', 'fig', 'raspberry', 'strawberry', 'cherry']
```

- Decorators are functions that accept other functions to be decorated - [[Decorators in python]]
  - They usually return a different inner function using the argument function

## Map, filter, and reduce

- They are high order functions
- They can be replaced by listcomp and genexp - [[Comprehension and generator expressions in Python]]
```python
>>> list(map(factorial, range(6)))  (1)
[1, 1, 2, 6, 24, 120]
>>> [factorial(n) for n in range(6)]  (2)
[1, 1, 2, 6, 24, 120]
>>> list(map(factorial, filter(lambda n: n % 2, range(6))))  (3)
[1, 6, 120]
>>> [factorial(n) for n in range(6) if n % 2]  (4)
[1, 6, 120]
```

## Anonymous Functions

- `lambda` functions
  - They don't have names, only bodies
- They are rare, but can be used with **high order functions**
- If they are big enough transform them into `def` function
```python

>>> fruits = ['strawberry', 'fig', 'apple', 'cherry', 'raspberry', 'banana']
>>> sorted(fruits, key=lambda word: word[::-1])
['banana', 'apple', 'fig', 'raspberry', 'strawberry', 'cherry']
```

### sources

- Fluent Python - Luciano Ramalho - 2023 - Second Edition - Web Edition

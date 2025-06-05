# Dictionary in python

## Unpacking dictionary
```python
>>> def dump(**kwargs):
...     return kwargs
...
>>> dump(**{'x': 1}, y=2, **{'z': 3})
{'x': 1, 'y': 2, 'z': 3}
```

## Joining mapping

```python
>>> d1 = {'a': 1, 'b': 3}
>>> d2 = {'a': 2, 'b': 4, 'c': 6}
>>> d1 | d2
{'a': 2, 'b': 4, 'c': 6}
```

## Userdict

- UserDict is the best class to be inherent to create a custom dictionary class with some already
  implemented special functions. The keys need to be hashable (has hash code that never change between
  it life cycle)

## setdefault

- `setdefault` puts a default value when a key is not found in dictionary
```python
WORD_RE = re.compile(r'\w+')
index = {}
with open(sys.argv[1], encoding='utf-8') as fp:
    for line_no, line in enumerate(fp, 1):
        for match in WORD_RE.finditer(line):
            word = match.group()
            column_no = match.start() + 1
            location = (line_no, column_no)
            index.setdefault(word, []).append(location)

for word in sorted(index, key=str.upper):
    print(word, index[word])
```

### defauldict

- Similar to `setdefault`, `defaultdict` put a default value as well.
```python
WORD_RE = re.compile(r'\w+')
index = collections.defaultdict(list)     # (1)
with open(sys.argv[1], encoding='utf-8') as fp:
    for line_no, line in enumerate(fp, 1):
        for match in WORD_RE.finditer(line):
            word = match.group()
            column_no = match.start() + 1
            location = (line_no, column_no)
            index[word].append(location)  # (2)

# display in alphabetical order
for word in sorted(index, key=str.upper):
    print(word, index[word])
```

[[]]
## Special methods
- `__missing__`, `__eq__` and `__hash__` are methods important to be implemented when inherent
  `UserDict` or `dict`

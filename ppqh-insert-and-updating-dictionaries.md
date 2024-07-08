# Insert and Updating Dictionaries
#python #datastructure #programming #language #O1

- There is some to insert elements and update them in using `dict` in Python
- We can use `setdefault` to set a default value when a `key` does not exist.

```python
import re
import sys
WORD_RE = re.compile(r'\w+')
index = {}
with open(sys.argv[1], encoding='utf-8') as fp:
    for line_no, line in enumerate(fp, 1):
        for match in WORD_RE.finditer(line):
            word = match.group()
            column_no = match.start() + 1
            location = (line_no, column_no)
            index.setdefault(word, []).append(location)
# display in alphabetical order
for word in sorted(index, key=str.upper):
    print(word, index[word])
```

- The following piece of code means `index.setdefault(word, []).append(location)`:
```python
if key not in my_dict:
    my_dict[key] = []
my_dict[key].append(new_value)
```
- The code above in other words, if a key does not exist put an empty list there, if exists append a value on the list
- It is possible to use `defauldict` as well
- `defaultdict` uses a `default_factory` to fill the key.

```python
index = collections.defaultdict(list) # Fill the key with a empty list
with open(sys.argv[1], encoding='utf-8') as fp:
    for line_no, line in enumerate(fp, 1):
        for match in WORD_RE.finditer(line):
            word = match.group()
            column_no = match.start() + 1
            location = (line_no, column_no)
```
- [[llom-how-to-handle-missing-on-dictionary]]#

### References
Ramalho, 2022, 83-96

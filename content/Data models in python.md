# Data models in python
#python #code

- Data models in python is a way to create pythonic code using special methods
- Special methods are methods called by the interpreter and not the coder itself
- ```__len__```, ```__getitem__``` and ```__setitem__``` are types of special methods
- [[```__getitem__``` special method]]# is related to index and iterator
- The following code is example of implementation of special method

```python
import collections

Card = collections.namedtuple('Card', ['rank', 'suit'])

class FrenchDeck:
    ranks = [str(n) for n in range(2, 11)] + list('JQKA')
    suits = 'spades diamonds clubs hearts'.split()

    def __init__(self):
        self._cards = [Card(rank, suit) for suit in self.suits
                                        for rank in self.ranks]

    def __len__(self):
        return len(self._cards)

    def __getitem__(self, position):
        return self._cards[position]
```

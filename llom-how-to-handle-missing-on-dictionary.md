# How to handle missing on dictionary
#python #datastructure #datamodel #programming #language

- `__missing__` deal with `keys` when its nos presented on the `dict`
- Try to use Inheritance From [[30x9-collections-userdict]] instead of `dict` because
   * It has already some methods implemented, `__get__` and `__update__`
   * it uses a `self.data` variable, which is a `dict`, to store values and key, avoiding recursion on `__setitem__` method
  and simplify `__contains__`.
- Key must be hashable: [[nxj2-hashable]]

```python
class StrKeyDict0(dict): # Using dict as superclass

    def __missing__(self, key):
        if isinstance(key, str):
            raise KeyError(key)
        return self[str(key)] # Transforming into string to avoid recursion

	def get(self, key, default=None):
        try:
            return self[key]
        except KeyError:
            return default

    def __contains__(self, key):
        return key in self.keys() or str(key) in self.keys()
```
- Now using `UserDict` for the difference:

```python
class StrKeyDict(collections.UserDict):

    def __missing__(self, key):
        if isinstance(key, str):
            raise KeyError(key)
        return self[str(key)]

    def __contains__(self, key):
        return str(key) in self.data # self.data object storing key and values

    def __setitem__(self, key, item):
        self.data[str(key)] = item
```

### References
Ramalho, 2022, p83-96

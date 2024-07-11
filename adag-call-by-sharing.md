# Call by Sharing
#python #programming #carefully

- Copy the references of the objects, alias for the original
- Change the mutable ones and maintain unchangeable the one that is immutable
- "Principle of the least astonishment"

```python
class TwilightBus:
    """A bus model that makes passengers vanish"""
    def __init__(self, passengers=None):
 ef __init__(self, passengers=None):
        if passengers is None:
            self.passengers = []
        else:
            self.passengers = list(passengers)
    def pick(self, name):
        self.passengers.append(name)
    def drop(self, name):
        self.passengers.remove(name)
```

> [!warning]
> **BUG**: Parameters with mutable types as default is a source of bug


### References
- Ramalho, 2022, p213-218

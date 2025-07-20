# Goose typing in python
#python #code #datastructure

- It uses `collections.abc` to create abstract base classes
- When a class inherit some collections like `MutableSequence` for example,
it get all the concrete methods from super class
  - Need to implement the abstract methods to be instantiate
- use of `isinstance` or `issubclass` to validate if a class is accepted on a specific
part of the code.
- Runtime checks of the code correctness

```python
from abc import ABC, abstractmethod
from math import pi

class Shape(ABC):
    @abstractmethod
    def area(self) -> float: ...

class Circle(Shape):
    def __init__(self, r: float) -> None:
        self.r = r

    def area(self) -> float:
        return pi * self.r ** 2

class Square(Shape):
    def __init__(self, side: float) -> None:
        self.side = side

    def area(self) -> float:
        return self.side ** 2

def paint_needed(shape: Shape, coverage: float) -> float:
    # opcional, mas ilustra o "goose check"
    if not isinstance(shape, Shape):
        raise TypeError("shape não implementa Shape ABC")
    return shape.area() / coverage
```

### sources
- Fluent Python - Luciano Ramalho - 2022 - Second Edition

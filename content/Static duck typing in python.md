# Static duck typing in python
#code #python

- Uses **PEP 544** protocols
- Structural type checked statically
- It not use inheritance, only need to have the method implemented
- Used with external tools like **Mypy**
- It has the flexibility of the Duck Typing - [[Duck Typing and Nominal Typing]]
  - But has static guarantees
- Limitations: need to have Python 3.8+ and IDE with checkers

```python
from typing import Protocol, runtime_checkable, List

@runtime_checkable              # opcional, permite isinstance em runtime
class SupportsArea(Protocol):
    def area(self) -> float: ...

class Triangle:                 # NÃO herda de nada
    def __init__(self, b: float, h: float) -> None:
        self.b, self.h = b, h

    def area(self) -> float:
        return 0.5 * self.b * self.h

def paint_needed(shape: SupportsArea, coverage: float) -> float:
    return shape.area() / coverage

def batch_paint(shapes: List[SupportsArea], coverage: float) -> float:
    return sum(s.area() for s in shapes) / coverage

# mypy aceita Triangle; ele “bate” estruturalmente
tri = Triangle(4, 5)
print(paint_needed(tri, 10))

# runtime check opcional
import inspect, math
assert isinstance(tri, SupportsArea)     # True
assert not isinstance(math, SupportsArea) # False
```

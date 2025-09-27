# Python Type Evolution
#python #code #datastructure #permanentnote

## Overview

Python evolve from a purely dynamic language to offer an complete spectrum options of typing, from duck typing to static
checker.

## Typings

### 1. Duck Typing
**Princípio**: "If walks like duck and do quack like duck it is a duck"

```python
def alert(birdie):  # Accept every object which have quack method
    birdie.quack()
```

**Características:**
- Maximum flexiblity
- Erros only in runtime
- Ideal to build prototypes
- Permit polymorphism without hierarchy

**Trade-off**: Flexibility vs early error detections

### 2. Nominal Typing:
**Princípio**: "The type matters more than the behavior"

```python
def alert_duck(birdie: Duck) -> None:
    birdie.quack()
```

**Características:**
-  Static check base on hierarchy
- Can reject valid code (false positive)
- Detect errors in compilation time

**Trade-off**: Security vs rigid

### 3. Goose Typing: O
**Princípio**:  "Explicit checker of capacities at runtime"

```python
from abc import ABC, abstractmethod

class Shape(ABC):
    @abstractmethod
    def area(self) -> float: ...

def paint_needed(shape: Shape, coverage: float) -> float:
    if not isinstance(shape, Shape):  # Runtime check
        raise TypeError("shape não implementa Shape ABC")
    return shape.area() / coverage
```

**Características:**
-  Combine hierarchy with runtime checker
-  Use `isinstance()` for validation
-  ABC give concrete methods without the necessity of implementation
-  Explicit control when check types

**Trade-off**: Control vs Verification Overhead

### 4. Static Duck Typing (Protocols):
**Princípio**: "Structural static check without hierarchy"

```python
from typing import Protocol, runtime_checkable

@runtime_checkable
class SupportsArea(Protocol):
    def area(self) -> float: ...

class Triangle:  # NÃO herda de nada!
    def area(self) -> float:
        return 0.5 * self.b * self.h

def paint_needed(shape: SupportsArea, coverage: float) -> float:
    return shape.area() / coverage  # mypy aprova!
```

**Características:**
-  Static check without forced hierarchy
-  Structural compatibility like duck typing
-  `@runtime_checkable` for optional validation
-  Better inference type

**Trade-off**:  Sophistication vs Conceptual complexity

##   Decision Matrix

| Situation                | Duck          | Nominal         | Goose        | Static Duck  |
|--------------------------|---------------|-----------------|--------------|--------------|
| **Fast Prototype**       | ✅ ideal      | ❌ rigid        | ⚡ Overhead  | ⚡ Complex   |
| **Public library**       | ❌ fragile    | ⚡ bouding      | ✅ Robust    | ✅ Flexible  |
| **Big team**             | ❌ ambiguous  | ⚡ perscriptive | ⚡ Verboso   | ✅ Clear     |
| **Legacy code**          | ✅ Compatible | ❌ Breaking     | ⚡ Migration | ✅ Gradual   |
| **Critical Performance** | ⚡ runtime    | ✅ Compile-time | ❌ Checks    | ✅ Zero-cost |

## Gradual evolution

### Strategy 1: Duck → Static Duck
```python
# Fase 1: Puro Duck Typing
def process_items(items):
    return [item.process() for item in items]

# Fase 2: Adicionar Protocol
from typing import Protocol

class Processable(Protocol):
    def process(self) -> Any: ...

def process_items(items: list[Processable]) -> list[Any]:
    return [item.process() for item in items]
```

### Strategy 2: Nominal → Protocol
```python
# Antes: Forçava herança
class FileHandler(ABC):
    @abstractmethod
    def read(self) -> str: ...

# Depois: Permite estruturas existentes
class Readable(Protocol):
    def read(self) -> str: ...

# Agora funciona com file objects built-in sem modificação!
```

## Original Insights

### 1. "Principle of locality typing"
Choose the strategy of typing shall be local to context, not global to project.

```python
# Interface pública: Protocol (máxima compatibilidade)
class DataProcessor(Protocol):
    def process(self, data: Any) -> Result: ...

# Implementação interna: Duck (velocidade de desenvolvimento)
def _internal_helper(obj):
    return obj.some_method()  # Sem tipos

# Validação crítica: Goose (controle explícito)
def public_api(processor: DataProcessor):
    if not isinstance(processor, SomeABC):
        raise TypeError("Incompatible processor")
```

## Conclusion:  Mental map for typing

- **Duck Typing**:  For exploration and flexiblity
- **Nominal Typing**:  For rigid contracts and clear hierarchies
- **Goose Typing**: ompatibilidade For explicit validation and compatibility
- **Static Duck**:  For expressive apis and static verification

---

### Sources
* [[Duck Typing and Nominal Typing]]
* [[Static Protocols]]
* [[Goose typing in python]]
* [[Static duck typing in python]]
* [[Type Hints]]

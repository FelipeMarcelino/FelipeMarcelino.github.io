# Python Data Structure Creation Patterns
#python #datastructure #designpatterns #permanentnote

## Core Concept

Python offers multiple approaches to create structured data, each with distinct trade-offs between simplicity, performance, type safety, and functionality. Understanding when to use each pattern is crucial for writing maintainable and efficient code.

## The Spectrum of Data Structure Patterns

### 1. Built-in Tuples (Simplest)
- **When:** Quick, temporary groupings of heterogeneous data
- **Trade-offs:** No named access, limited readability for complex structures
- **Best for:** Coordinates, RGB values, simple return values

```python
point = (3, 4)  # Simple but lacks semantic meaning
```

### 2. Named Tuples (collections.namedtuple)
- **When:** Need named access with minimal overhead
- **Trade-offs:** Runtime creation, limited IDE support, no type hints
- **Best for:** Simple records where performance matters

```python
Point = namedtuple('Point', ['x', 'y'])
p = Point(3, 4)  # p.x, p.y accessible
```

### 3. Typed Named Tuples (typing.NamedTuple)
- **When:** Want type safety with named tuple benefits
- **Trade-offs:** Better IDE support than collections.namedtuple, still immutable
- **Best for:** Type-safe simple records

```python
class Point(NamedTuple):
    x: int
    y: int
```

### 4. Data Classes (Most Versatile)
- **When:** Need mutable objects with rich functionality
- **Trade-offs:** More memory overhead, but maximum flexibility
- **Best for:** Complex business objects, API models, configuration objects

```python
@dataclass
class Point:
    x: int
    y: int

    def distance_from_origin(self) -> float:
        return (self.x ** 2 + self.y ** 2) ** 0.5
```

## Decision Matrix

| Pattern | Mutability | Type Hints | Methods | Performance | IDE Support |
|---------|------------|------------|---------|-------------|-------------|
| tuple | ❌ | ❌ | ❌ | ⭐⭐⭐⭐⭐ | ⭐⭐ |
| namedtuple | ❌ | ❌ | Limited | ⭐⭐⭐⭐ | ⭐⭐⭐ |
| NamedTuple | ❌ | ✅ | Limited | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ |
| dataclass | ✅ | ✅ | ✅ | ⭐⭐⭐ | ⭐⭐⭐⭐⭐ |

## Evolution Path

Most projects naturally evolve along this progression:

1. **Start with tuples** for rapid prototyping
2. **Upgrade to NamedTuple** when readability becomes important
3. **Move to dataclass** when you need methods or mutability
4. **Add custom methods** as business logic grows

## Key Insights

**Immutability vs Flexibility:** Early patterns prioritize immutability and performance, later patterns prioritize flexibility and maintainability.

**Type Safety Evolution:** Python's approach shows gradual adoption of type safety—from no types (tuple) to full type support (dataclass).

**Performance Trade-offs:** More features generally mean more overhead, but the difference is often negligible in practice.

## Practical Guidelines

**Choose tuple when:** You need a quick, temporary grouping and performance is critical.

**Choose NamedTuple when:** You want immutable records with named access and type safety.

**Choose dataclass when:** You need a full-featured class with methods, mutability, or complex initialization.

**Don't overthink it:** You can always refactor from simpler to more complex patterns as requirements evolve.

---

### Source

- [[Dataclass, collections.namedtuple and typing.NamedTuple]]
- [[Tuple: records and immutable list]]

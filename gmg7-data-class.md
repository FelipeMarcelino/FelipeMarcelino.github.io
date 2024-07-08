# Data Class
#datastructure #programming #data #storage #python

- Data class are the most complexity storage class on python compare to the [[01o9-collections-namedtuple]] and [[07fk-typing-namedtuple]]
- They are `mutable`, but can be `immutable` if you set the parameter `frozen=true`
	- If `mutable`, no type checking
- Data class does not modify the type, is not dependent of inheritance neither metaclass
- Class syntax
- Default methods implemented are: `__init__`, `__repr__`, `__eq__`
- If `eq=true and frozen=true` then the class is `hashable`
- `Fields` are initialized by `__init__`

> [!warning]
> **BUG**: Mutable variable as default value. Use `default_factory`

```python
@dataclasss
class ClubMember:
	name: str
	guests: list = field(default_factory=list) # provide a function on the default_factory
```

- Data class has `post_init` when you need to make something after the initialization of the fields
- In addition, it is possible to pass `init_var` as well. This is variable used to initialize other
  variables and are not field neither class attribute

```python
@dataclass
class HackerClubMember(ClubMember):
	all_handles: ClassVar[set[str]] = set()
    handle: str = ''
    def __post_init__(self):
        cls = self.__class__
        if self.handle == '':
            self.handle = self.name.split()[0]
        if self.handle in cls.all_handles:
            msg = f'handle {self.handle!r} already exists.'
            raise ValueError(msg)
        cls.all_handles.add(self.handle)

@dataclass
class C:
    i: int
    j: int = None
    database: InitVar[DatabaseType] = None
    def __post_init__(self, database):
        if self.j is None and database is not None:
            self.j = database.lookup('j')
c = C(10, database=my_database)
```

- [[sws0-data-class-as-code-smell]]#
- [[26qw-pattern-matching-as-data-class]]#

### References
- Ramalho, 2022, p172-179
- Ramalho, 2022, p179-183

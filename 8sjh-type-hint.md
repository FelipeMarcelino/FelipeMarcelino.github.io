# Type Hint
#python #programming #doc #typing #datamodel

- Types are defined by supported operations
- It is a documentation which can be checked by `type checkers` like `MyPy`
- There is no impact on the execution of the code
- How is: `var_name: some_type` (PEP 484)
- It is not possible to make hints ever on the code, sometimes is quite impossible
- PEP 484
- [[yyih-duck-typing-vs-nominal-typing]]#
- Some options that can be important for `mypy` tools
	- disallow-untyped-defs: not allow any function without type hint
	- disallow-incomplete-defs: not allow any function with incomplete type hint
- `mypy` can have global configuration or have `mypy.ini` for each module
- Give no space between `:` and variable and one space between the `:` and type
- `=` space on both sides
- You can use `default` value `None` with two syntax and `Optional`
	- `def show_count(count: int, singular: str, plural: Optional[str] = None)`
	- `def show_count(count: int, singular: str, plural: str | None = None)`
- `Any` is a magic type which allow any operations and subclasses, therefore accept anything
- Simply type annotation: `str, float, int, bytes or classes`
- `Union[A, B, Union[C, D, E]] = Union[A, B, C, D, E]`
- Generic Collections example:
- `NoReturn` usually used for function that raises exception

```python
def tokenize(text: str) -> list[str]:
    return text.upper().split()
```
- Code above return a list of string
- [[o4v3-typing-tuple]]#
- [[0c3b-typing-maps]]#
- `Sequence` or `Iterable` for parameters and `list` for return type
- [[80tb-typing-callable]]#
- [[m30e-parameterized-generics-and-typevar]]#
- [[zon5-annotating-positional-only-and-variadic-parameters]]#

> [!warning]
> Avoid `Optional` and `Union` on return types, because the user need to test which type of variable was returned by the
> function

> [!tip] Collection Type Parameters
> Use one of them `int`, `float`, `complex`<br>
> Use `Union[float, Decimal, Fraction]`<br>
> Use `Iterable` instead of `Sequence`<br>
> Use `Iterator` for return type on generator

```python
from collections.abc import Iterable
FromTo = tuple[str, str]
def zip_replace(text: str, changes: Iterable[FromTo]) -> str:
    for from_, to in changes:
        text = text.replace(from_, to)
    return text
```

### References
- Ramalho, 2022, p172-179
- Ramalho, 2022, p253-260
- Ramalho, 2022, p260-265
- Ramalho, 2022, p294

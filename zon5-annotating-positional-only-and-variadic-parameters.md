# Annotating Positional Only and Variadic Parameters
#python #programming #function #doc #typing

```python
def tag(
	name: str,
	/,
	* content: str, # tuple[str, ...]
	class_: Optional[str] = None,
	**attrs: str, # dict[str, str]
) -> str:
```

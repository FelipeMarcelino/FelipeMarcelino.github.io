# Python Variable Scope
#python #rules #programming #scope

- Variable has scope, and exist precedence regarding the local of reading values (local then global)
- If you want to read global variables with variable local with the same name is possible to use `global <variable
  name>`. Example below:

```python
>>> b = 6
>>> def f3(a):
...     global b
...     print(a)
...     print(b)
...     b = 9
...
>>> f3(3)
3
6
>>> b
9
```

- [[ig5o-closures]]# is a form to deal with **Free Variables**

## Logic Lookup


- There is a global `x` declaration, `x` comes from and is assigned to the `x` global
variable module.
- There is a non-local `x` declaration, `x` comes from and is assigned to the `x` local
variable of the nearest surrounding function where x is defined.
- `x` is a parameter or is assigned a value in the function body, then `x` is the local
variable.
- If `x` is referenced but is not assigned and is not a parameter:
	- `x` will be looked up in the local scopes of the surrounding function bodies
(non-local scopes).
	- If not found in surrounding scopes, it will be read from the module global
scope.
	- If not found in the global scope, it will be read from `__builtins__.__dict__`

### References
- Ramalho, 2022, 308-311
- Ramalho, 2022, 315-317

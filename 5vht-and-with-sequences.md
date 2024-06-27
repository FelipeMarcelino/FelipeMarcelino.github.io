# + and * with Sequences
#python #programming #language #efficiency

- It is the operation `_add_` and `_mul_`.
- `a += b` is the operation `_iadd_`. When it is not implemented, the **fallback** is the `_add_`
- `_iadd_` is the `list.extend()`. Is the same for `bytearray` and `array.array`.
- For `immutable` objects, the `_iadd_` is similar to the `_add_`.

> [!warning]
> **PERFORMANCE**: Append on `imutable` objects are inefficient

> [!warning]
> **BUG**: Does not put `mutable` objects on `immutable` ones.

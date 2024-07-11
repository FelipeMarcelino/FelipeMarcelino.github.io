# Difference between is and ==
#python #datamodel #programming #comparison

- `is` compare the **reference** or the `id` of the object, otherwise `==` compare the **values**.
- `is` is faster than `==` because it does not implement `__eq__` in python
- `is` usually is used to compare to **Singleton** objects like `None`

```python
x is None
```

### References
- Ramalho, 2022, p201-208

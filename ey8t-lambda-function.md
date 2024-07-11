# Lambda Function
#python #programming #functional

- They are anonymous function, they do not receive name
- If they are too complex transform them into `def`, or, normal function
- Can be used the [[z7l7-walrus]] operator to assign instead of the `=`, however, it is not recommended
- They are used as argument for high order functions

```python
>>> fruits = ['strawberry', 'fig', 'apple', 'cherry', 'raspberry', 'banana']
>>> sorted(fruits, key=lambda word: word[::-1])
['banana', 'apple', 'fig', 'raspberry', 'strawberry', 'cherry']
```

### References
- Ramalho, 2022, p236-237

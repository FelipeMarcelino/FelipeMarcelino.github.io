# listcomp
#python #programming #language #efficiency

* It does what `filter` and `map` do.

Example of `listcomp` or list comprehension:

```python

elems = [1 2 3 4]
aux = [elem for elem in elems]

```

`listcomp` create a new list, so it is necessary to allocate a whole list to manipulate a `listcomp`.
There is a special case known as [[z7l7-walrus]] operator.

`listcomp` use more memory than [[0651-genexp]] because last one does not allocate and deal with the element one by one.

> [!tip] [[pcvu-sort-and-sorted]]
> Both `sort` and `sorted` are made to sort sequences. However, `sort` does is `in-place` while `sorted` produce
> another object.

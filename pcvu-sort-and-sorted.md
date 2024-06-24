# Sort and Sorted
#algorithm #python #language #programming #efficiency

- `Sort` and `sorted` in python are to organize elements in a specific order
- They have two `keywords`: `key` and `reverse`
   * key: receive a function with one argument to be pass the element to be compared to other
   * reverse: if the order is reversed
- `Sort` does not return a new object while but `sorted` returns, so the former is `in-place`, in that way less memory
  is used.
- Sorted objects are faster to be searched by any algorithm

> [!warning]
> For immutable objects like [[82os-python-tuples]] sort need to return a new object because the object is not mutable
> or no changeable.

### References
Ramalho, 2022, p56-58

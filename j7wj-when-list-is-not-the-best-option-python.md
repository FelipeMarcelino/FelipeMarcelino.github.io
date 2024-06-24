# When list is not the best option (Python)
#python #programming #language #datastructure #efficiency

- List are flexible but not suitable for all the time
- `array.array` can be used when the sequence of numbers are only numbers, saving memory
- `bytes` and `bytearray` can be used for images
- `memoryviews` are used when you want to use slices of arrays. They are generalized `Numpy` arrays. They shared memory
  bnetween data structures without the need to copy it.
```python
>>> octets = array('B', range(6))
>>> m1 = memoryview(octets)
>>> m1.tolist()
[0, 1, 2, 3, 4, 5]
>>> m2 = m1.cast('B', [2, 3])
>>> m2.tolist()
[[0, 1, 2], [3, 4, 5]]
>>> m3 = m1.cast('B', [3, 2])
>>> m3.tolist()
[[0, 1], [2, 3], [4, 5]]
>>> m2[1,1] = 22
>>> m3[1,1] = 33
>>> octets
array('B', [0, 1, 2, 33, 22, 5])
```

```python
>>> numbers = array('h', [-2, -1, 0, 1, 2])
>>> memv = memoryview(numbers)
>>> len(memv)
5
>>> memv[0]
-2
>>> memv_oct = memv.cast('B')
>>> memv_oct.tolist()
[254, 255, 255, 255, 0, 0, 1, 0, 2, 0]
>>> memv_oct[5] = 4
>>> numbers
array('h', [-2, -1, 1024, 1, 2]) # Here we change the bits 0000010000000000
```

### References

Ramalho, 2022, p59-70

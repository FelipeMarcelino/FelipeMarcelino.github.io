# classmethod
#class #python #programming

- `classmethod` receives the class itself
	- Can be used as constructor for example. It is possible to use `frombytes` to load object for a specific class

```python
@classmethod
def frombytes(cls, octets):
	typecode = chr(octets[0])
	memv = memoryview(octets[1:]).cast(typecode) #
	return cls(*memv)
```

### References
- Ramalho, 2022, p368-370

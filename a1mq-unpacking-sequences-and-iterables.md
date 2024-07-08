# Unpacking Sequences and Iterable
#python #programming #datastructure #language

- Works with any iterable: #[[aw9b-python-list]], #[[9n4u-python-dictionary]], #[[82os-python-tuples]]
- Parallel assignment

```python
# tuples
>>> lax_coordinates = (33.9425, -118.4080)
>>> latitude, longitude = lax_coordinates
>>> latitude
33.9425

>>> T = (20, 8)
>>> divmod(*t)
(2,4)
```
- Getting the last part
```python
>>> _ , filename = os.path.split('/home/luciano.ssh/id.rsa.pub')
>>> filename
'id_rsa.pub'
```

- Getting the excess
```python
>>> a, b, *rest = range(5)
>>> a, b, rest
(0, 1, [2,3,4])
>>> a, *body, c, d = range(5)
>>> a, body, c, d
(0, [1,2], 3, 4)
>>> fun(*[1,2],3,*range(4,7))
>>> *range (4), 4
(0,1,2,3,4)
>>> [*range(4),4]
[0,1,2,3,4]
```
* Dictionaries
```python
>>> def dump(*kwargs)
	return
>>> dump(**{'x':1}, y=2, **{'z':3})
{'x':1, 'y':2, 'z':3}
>>> {'a':0, **{'x':1}, 'y':2, *{'z':3,'x':4}} # In that case the second x overlap the value of the first one.
```

There another way to unpacking things in pythons, it is [[phk2-pattern-matching-or-destructuring]]#

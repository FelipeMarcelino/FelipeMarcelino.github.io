# Tuple: records and immutable list

- List can be approach with two different ways
    - as list with fixed size. Tuple uses less memory than mutable list
    - as records store using the specified field order to keep the records organized in a logic way
- Register example:
```python
>> lax_coordinates = (33.9425, -118.408056)  (1)
>>> city, year, pop, chg, area = ('Tokyo', 2003, 32_450, 0.66, 8014)  (2)
>>> traveler_ids = [('USA', '31195855'), ('BRA', 'CE342567'),  (3)
...     ('ESP', 'XDA205856')]
>>> for passport in sorted(traveler_ids):  (4)
...     print('%s/%s' % passport)   (5)
...
BRA/CE342567
ESP/XDA205856
USA/31195855
>>> for country, _ in traveler_ids:  (6)
...     print(country)
...
USA
BRA
ESP
```

- Immutable list example:
```python
>>> a = (10, 'alpha', [1, 2])
>>> b = (10, 'alpha', [1, 2])
>>> a == b
True
>>> b[-1].append(99)
>>> a == b
False
>>> b
(10, 'alpha', [1, 2, 99])
```

- If tuples has mutable elements on it, it can be a source of bug, so avoid mutable elements like list

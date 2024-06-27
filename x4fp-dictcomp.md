# dictcomp
#python #programming #language #datastructure

- Similar to [[ndtq-listcomp]], dictcomp is a way to create `dict` object using an iterable code for `key:value`.
- | and =| are used to merge dictionary/maps

```python
>>> dial_codes = [                                                  # <1>
    (880, 'Bangladesh'),
    (55,  'Brazil'),
    (86,  'China'),
    (91,  'India'),
    (62,  'Indonesia'),
    (81,  'Japan'),
    (234, 'Nigeria'),
    (92,  'Pakistan'),
    (7,   'Russia'),
    (1,   'United States'),
]
>>> country_dial = {country: code for code, country in dial_codes}
>>> country_dial
{'Bangladesh': 880,
 'Brazil': 55,
 'China': 86,
 'India': 91,
 'Indonesia': 62,
 'Japan': 81,
 'Nigeria': 234,
 'Pakistan': 92,
 'Russia': 7,
 'United States': 1}
 >>> {code: country.upper()
    for country, code in sorted(country_dial.items())
    if code < 70}
{55: 'BRAZIL', 62: 'INDONESIA', 7: 'RUSSIA', 1: 'UNITED STATES'}
```

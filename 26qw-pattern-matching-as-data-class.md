# Pattern Matching with Data Class
#python #programming #datastructure

- In fact, can be used with any type of class
- Pattern Matching can be **Simple** with sequences: [[phk2-pattern-matching-or-destructuring]]
- There is Pattern Matching with **Keyword**

```python
import typing
class City(typing.NamedTuple):
    continent: str
    name: str
    country: str
cities = [
    City('Asia', 'Tokyo', 'JP'),
    City('Asia', 'Delhi', 'IN'),
    City('North America', 'Mexico City', 'MX'),
    City('North America', 'New York', 'US'),
    City('South America', 'São Paulo', 'BR'),
]

def match_asian_cities():
    results = []
    for city in cities:
        match city:
            case City(continent='Asia'):
                results.append(city)
    return results
```

- And there is **Positional**, where the order of the attribute matters

```python
def match_asian_countries_pos():
    results = []
    for city in cities:
        match city:
            case City('Asia', _, country):
                results.append(country)
    return results
```

- [[toej-supporting-positional-pattern-matching-with-classes]]#

### References
Ramalho, 2022, p190-196

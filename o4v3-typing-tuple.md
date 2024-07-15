# Typing Tuple
#python #typing #programming #doc


- Using [[82os-python-tuples]] as record it is possible to type it as well
```python
from geolib import geohash as gh  # type: ignore
PRECISION = 9
def geohash(lat_lon: tuple[float, float]) -> str:
    return gh.encode(*lat_lon, PRECISION)
```

- Tuple as immutable sequence
```python
from collections.abc import Sequence
def columnize(
    sequence: Sequence[str], num_columns: int = 0
) -> list[tuple[str, ...]]:
    if num_columns == 0:
        num_columns = round(len(sequence) ** 0.5)
    num_rows, reminder = divmod(len(sequence), num_columns)
    num_rows += bool(reminder)
    return [tuple(sequence[i::num_rows]) for i in range(num_rows)]
```

### Rerefences
- Ramalho, 2022, p274-276

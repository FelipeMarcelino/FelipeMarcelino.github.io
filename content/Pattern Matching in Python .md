# Pattern Matching in Python

- Pattern matching in python uses `case` and `match`
- Both `dictionaries`,`tuples` and `sequences` can be used inside match procedures.
- Pattern matching abuses of technique destructuring

Using dictionaries:
```python
def get_creators(record: dict) -> list:
    match record:
        case {'type': 'book', 'api': 2, 'authors': [*names]}:  # (1)
            return names
        case {'type': 'book', 'api': 1, 'author': name}:  # (2)
            return [name]
        case {'type': 'book'}:  # (3)
            raise ValueError(f"Invalid 'book' record: {record!r}")
        case {'type': 'movie', 'director': name}:  # (4)
            return [name]
        case _:  # (5)
            raise ValueError(f'Invalid record: {record!r}')
```

Using Sequences:
```python
 def handle_command(self, message):
        match message:  # (1)
            case ['BEEPER', frequency, times]:  # (2)
                self.beep(times, frequency)
            case ['NECK', angle]:  # (3)
                self.rotate_neck(angle)
            case ['LED', ident, intensity]:  # (4)
                self.leds[ident].set_brightness(ident, intensity)
            case ['LED', ident, red, green, blue]:  # (5)
                self.leds[ident].set_color(ident, red, green, blue)
            case _:  # (6)
                raise InvalidCommand(message)
```

## Some corner cases

```python
def main():
    print(f'{"":15} | {"latitude":>9} | {"longitude":>9}')
    for record in metro_areas:
        match record:  # (1)
            case [name, _, _, (lat, lon)] if lon <= 0:  # (2)
                print(f'{name:15} | {lat:9.4f} | {lon:9.4f}')

match tuple(phone):
        case ['1', *rest]:  # North America and Caribbean
            ...
        case ['2', *rest]:  # Africa and some territories
            ...
        case ['3' | '4', *rest]:  # Europe
            ...

case [name, _, _, (lat, lon) as coord]:

case [str(name), *_, (float(lat), float(lon))]:

```

- Using pattern match with class implemented by the user:

```python
def evaluate(exp: Expression, env: Environment) -> Any:
    "Evaluate an expression in an environment."
    match exp:
    # ... lines omitted
        case ['quote', x]:  # (1)
            return x
        case ['if', test, consequence, alternative]:  # (2)
            if evaluate(test, env):
                return evaluate(consequence, env)
            else:
                return evaluate(alternative, env)
        case ['lambda', [*parms], *body] if body:  # (3)
            return Procedure(parms, body, env)
        case ['define', Symbol() as name, value_exp]:  # (4)
            env[name] = evaluate(value_exp, env)
        # ... more lines omitted
        case _:  # (5)
            raise SyntaxError(lispstr(exp))
```
- In the case above `Symbol` is a class implemented by the user and we can use to match it on the pattern matching

# Duck Typing and Nominal Typing
#code #datastructure #python

## Duck Typing

- Used when we want to pass a type that does matter only the operations that it supports
- More flexible than **nominal typing**

## Nominal Typing

- The implementation of the class/function means a lot here
- The checker only check the source code where variables have type hints
- More rigid than **duck typing**

## Code
```python
class Bird:
    pass

class Duck(Bird):  # (1)
    def quack(self):
        print('Quack!')

def alert(birdie):  # (2)
    birdie.quack()

def alert_duck(birdie: Duck) -> None:  # (3)
    birdie.quack()

def alert_bird(birdie: Bird) -> None:  # (4)
    birdie.quack()

from birds import *

daffy = Duck()
alert(daffy)
alert_duck(daffy)
alert_bird(daffy)
…/birds/ $ mypy daffy.py
birds.py:16: error: "Bird" has no attribute "quack"
Found 1 error in 1 file (checked 1 source file)
…/birds/ $ python3 daffy.py
Quack!
Quack!
Quack!
```

- Sometimes the checker has false positives
- Duck typing is more flexible and easy for newcomers but permits operations not supported cause errors
during the execution. In nominal detect errors before the execution, but sometimes reject code that
will be executed without errors

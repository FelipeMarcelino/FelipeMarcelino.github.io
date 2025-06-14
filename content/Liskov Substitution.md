# Liskov Substitution
#theory #code

```python
class T1:
    ...

class T2(T1):
    ...

def f1(p: T1) -> None:
    ...

o2 = T2()

f1(o2)  # OK
```

- Liskov substitution say that every object t2 subclass of t1, where t1 is accepted, t2 will be accepted
  as well. But the opposite is not true because t2 can implement additional methods, so t1 cannot
  be used in the place where t2 is accepted.

# Parameterized Decorators
#python #decorator #designpattern #programming

- To create a decorator with parameters is necessary to build a **decorator factory**
	- This decorator factory will accept parameter and pass to the decorator itself

```python
registry = set()
def register(active=True):
    def decorate(func):
        print('running register'
              f'(active={active})->decorate({func})')
        if active:
            registry.add(func)
        else:
            registry.discard(func)
        return func
    return decorate
@register(active=False)
def f1():
    print('running f1()')
@register()
def f2():
    print('running f2()')
def f3():
    print('running f3()')

>>> from registration_param import *
running register(active=False)->decorate(<function f1 at 0x10073c1e0>)
running register(active=True)->decorate(<function f2 at 0x10073c268>)
>>> registry
{<function f2 at 0x10073c268>}
>>> register()(f3)
running register(active=True)->decorate(<function f3 at 0x10073c158>)
<function f3 at 0x10073c158>
>>> registry
{<function f3 at 0x10073c158>, <function f2 at 0x10073c268>}
>>> register(active=False)(f2)
running register(active=False)->decorate(<function f2 at 0x10073c268>)
<function f2 at 0x10073c268>
>>> registry
{<function f3 at 0x10073c158>}
```

- Code above use the concept of [[ig5o-closures]] and has normal call as well `register()(f3)`
- [[wmjn-python-decorator-implementation]] but with parameters:
  [[aswx-python-decorator-implementation-with-parameters]]#

### References
- Ramalho, 2022, p329-335

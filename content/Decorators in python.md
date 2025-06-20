# Decorators in python
#code #python #datastructure

- Decorators is being use to decorate functions
- They execute some process related to decorated function or return decorated function or replace by another function
```python
>>> def deco(func):
...     def inner():
...         print('running inner()')
...     return inner  (1)
...
>>> @deco
... def target():  (2)
...     print('running target()')
...
>>> target()  (3)
running inner()
>>> target  (4)
<function deco.<locals>.inner at 0x10063b598>
```
- They are synthetic sugar
- They executed in `import` time or the modules are being imported
```python

registry = []  # (1)

def register(func):  # (2)
    print(f'running register({func})')  # (3)
    registry.append(func)  # (4)
    return func  # (5)

@register  # (6)
def f1():
    print('running f1()')

@register
def f2():
    print('running f2()')

def f3():  # (7)
    print('running f3()')

def main():  # (8)
    print('running main()')
    print('registry ->', registry)
    f1()
    f2()
    f3()

if __name__ == '__main__':
    main()  # (9)
python3 registration.py
running register(<function f1 at 0x100631bf8>)
running register(<function f2 at 0x100631c80>)
running main()
registry -> [<function f1 at 0x100631bf8>, <function f2 at 0x100631c80>]
running f1()
running f2()
running f3()
```

- Usually decorators are implemented in one module and used in another module
- Usually decorators return and define inner function
- Using decorators to implement design pattern strategy: [[Strategy using functions]]

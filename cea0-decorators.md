# Python Decorators
#python #designpattern #programming #decorator

- Is a type of #[[dcdy-callable-objects]]
- The objective: Decorate another function and take this function as argument
- Most part of the decorators change the function decorated
- Decorators are defined in one module and used and other modules as well
- They run on the step of `import time`

```python
@decorate
def target():
	print("running target")
```
- Code above transform into: `target = decorate(target)`

```python
#file registration.py
registry = []
def register(func):
    print(f'running register({func})')
    registry.append(func)
    return func
@register
def f1():
    print('running f1()')
@register
def f2():
    print('running f2()')
def f3():
    print('running f3()')
def main():
    print('running main()')
    print('registry ->', registry)
    f1()
    f2()
    f3()
if __name__ == '__main__':
    main()

$python registration.py
running register(<function f1 at 0x100631bf8>)
running register(<function f2 at 0x100631c80>)
running main()
registry -> [<function f1 at 0x100631bf8>, <function f2 at 0x100631c80>]
running f1()
running f2()
running f3()
```

```python
>>> import registration
running register(<function f1 at 0x10063b1e0>)
running register(<function f2 at 0x10063b268>)
>>> registration.registry
[<function f1 at 0x10063b1e0>, <function f2 at 0x10063b268>]
```
- [[wmjn-python-decorator-implementation]]#
- [[aswx-python-decorator-implementation-with-parameters]]#
- [[naei-cache-lru-cache-singledispatch]]#
- [[hl16-parameterized-decorators]]#

> [!tip] Quote
> * A decorator is a function or another callable<br>
> * A decorator may replace decorated function with a different one<br>
> * Decorators are executed immediately when a module is loaded<br>
> Ramlho, 2022, p306

### References
- Ramalho, 2022, p302-307

# Keyword Only Arguments
#python #programming #functions #howtodo

- * and ** [[a1mq-unpacking-sequences-and-iterables]]

```python
def tag(name, *content, class_=None, **attrs):
    """Generate one or more HTML tags"""
    if class_ is not None:
        attrs['class'] = class_
    attr_pairs = (f' {attr}="{value}"' for attr, value
                    in sorted(attrs.items()))
    attr_str = ''.join(attr_pairs)
    if content:
        elements = (f'<{name}{attr_str}>{c}</{name}>'
                    for c in content)
        return '\n'.join(elements)
    else:
        return f'<{name}{attr_str} />'

>>> tag('br')
'<br />'
>>> tag('p', 'hello')
'<p>hello</p>'
>>> print(tag('p', 'hello', 'world'))
<p>hello</p>
<p>world</p>
>>> tag('p', 'hello', id=33)
'<p id="33">hello</p>'
>>> print(tag('p', 'hello', 'world', class_='sidebar'))
<p class="sidebar">hello</p>
<p class="sidebar">world</p>
>>> tag(content='testing', name="img")
'<img content="testing" />'
>>> my_tag = {'name': 'img', 'title': 'Sunset Boulevard',
...           'src': 'sunset.jpg', 'class': 'framed'}
>>> tag(**my_tag)
'<img class="framed" src="sunset.jpg" title="Sunset Boulevard" />'
```

- Code above allow you call the function with different number of parameters because of `*content` and `**attrs`.
- Now let force the keyword arguments in the next code
```python
>>> def f(a, *, b): # * force the argument be a keyword, without default value
		return a,b
>>> f(1, b=2)
>>> f(1, 2) # Give a error: takes 1 positional argument but 2 were given
```
- Positional only:
```python
>>> def divmod(a,b,/) # / Force positional only
		return (a // b, a % b)
```

# Slicing
#python #programming #datastructure #language

- `s[a:b:c]`, `a` and `b` are first and second dimension, `c` is the **stride**.
- It is possible to use **slicing** to assign values

```python
>>> s = 'bicycle'
>>> s[::3]
'bye'
>>> s[::-1]
'elcycle'
>>> s[::-2]
'eccb' #bicycle
>>> l = list(range(10))
>>> l[3::3] = [11,22]
[0,1,20,11,5,22,9]
```

```python
>>> invoice = """
0.....6.................................40........52...55........
1909 Pimoroni PiBrella                      $17.50    3    $52.50
1489 6mm Tactile Switch x20                  $4.95    2    $9.90
1510 Panavise Jr. - PV-201                  $28.00    1    $28.00
1601 PiTFT Mini Kit 320x240                 $34.95    1    $34.95
"""

>>> SKU = slice(0, 6)
>>> DESCRIPTION = slice(6, 40)
>>> UNIT_PRICE = slice(40, 52)
>>> QUANTITY = slice(52, 55)
>>> ITEM_TOTAL = slice(55, None)
>>> line_items = invoice.split('\n')[2:]
>>> for item in line_items:
    print(item[UNIT_PRICE], item[DESCRIPTION])
$17.50   imoroni PiBrella
$4.95   mm Tactile Switch x20
$28.00   anavise Jr. - PV-201
$34.95   iTFT Mini Kit 320x240
```

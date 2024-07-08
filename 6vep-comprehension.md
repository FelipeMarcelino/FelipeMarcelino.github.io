# Comprehension
#python #datastructure #efficiency

- [[x4fp-dictcomp]]#
- [[ndtq-listcomp]]#
- [[n803-setcomp]]#
- [[0651-genexp]]#

- Both `dict` and `set` use braces `{}` to initialize comprehension
   * The difference on what will be the final result depends on which is provide inside braces
- Generation expression does not initialize a list, in that case **saves more memory**
   * Used with tuples and other type of sequences (array.array for example)
   * One element is treated per time
- On `array.array` for generation expression you can pass the type of the natural number.
- List comprehension are faster than `genexp`, but can only save the result as `List`, while `genexp` can save in any
  iterable type.

### Reference
- https://medium.com/@vinodkumargr/list-dictionary-and-set-comprehension-in-python-9823719a67da

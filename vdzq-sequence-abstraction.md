# Sequence Abstraction
#clojure #language #programming

**Sequence**: Set of elements linearly ordered
Everything is a sequence can treat as sequence. This is the principal philosophical statement behind Clojure language programming.
It is possible to apply `map` and `reduce` in a sequence because it is composed by three different operations: [[qkll-first-rest-and-cons]]#.
Is it possible to call seq operations is used by [[bjzo-clojure-seq-functions]]#. All data abstractions in Clojure can be transformed into
sequence if it has the following operation above.

Clojure deals with Sequence using `Indirection` or in other words `Polymorphism`.
- Seq → List
- Map → List of Vectors
- List of Vectors (**into** - it is a function) → Map

Seq operations return sequence as well.

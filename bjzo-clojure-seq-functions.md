# Clojure Seq Functions
#clojure #programming #functional #language

Clojure Sequence Functions use seq on their arguments and use the [[vdzq-sequence-abstraction]] as you definition.

## Map
Is a function that receive a collection of numbers or/and collection of functions

```clojure
	(def identities
	[{:alias "Batman"	:real "Bruce Wayne"}
	 {:alias "Spider Man"	:real "Peter Park"}
	 {:alias "Santa"	:real "Your mom"}
	 {:alias "Easte Bunny"	:real "Your dad"}])

	 (map :real identities)
	 ; => ("Bruce Wayne" "Peter Park" "Your mom" "Your dad")


	 (def sum #(reduce + %))
	 (def avg #(/ (sum %)(count %)))
	 (defn stats
			[numbers]
			(maps #(% numbers)[sum cont avg]))

	(stats [3 4 10])
	; => (17 3 17/3)
```

## Reduce

Reduce is a function with the objective to get a pair of a number and two number and reduce to one number using this
function. This can be used to change a value of ```hash-map``` for example or to `filter` a value on ```hash map```.

```clojure
	(reduce (fn [new-key [key val]]
	(assoc new-map key (inc val)))
	{}
	{:max 30 :min 10})
	; => {:max 31 :min 11}

	(reduce (fn [new-map [key val]]
	(if (> val 3)
	(assoc new-map key val)
	 new-map))
	 {}
	 {:human 4.1 :critter 3.0})
	 ; => {:human 4.1}
```

## Take and Drop

Take and Drop are functions to get elements from the beginning of the list or drop from the beginning of the drops

## Drop-While, Take-While and Filter

Drop-While and Take-While are functions that use a `predicate function` to test the conditional and while the
conditional is true the element is taking or dropping by the function. It is possible to simulate filter using Take-While
and Drop-While at same time if the elements of the list are ordered, and it is more efficient than the filter itself because not every
element of the list is read by the function.

```clojure
	(def food-journal
	[{:month 1 :day 1 :human 5.3 :critter 2.3}
	{:month 1 :day 2 :human 5.1 :critter 2.0}
	{:month 2 :day 1 :human 4.9 :critter 2.1}
	{:month 2 :day 2 :human 5.0 :critter 2.5}
	{:month 3 :day 1 :human 4.2 :critter 3.3}
	{:month 3 :day 2 :human 4.0 :critter 3.8}
	{:month 4 :day 1 :human 3.7 :critter 3.9}
	{:month 4 :day 2 :human 3.7 :critter 3.6}
	])

	(take-while #(< (:month %) 4)
				(drop-while #(< (:month %) 2) food-journal))
; ->
	({:month 2 :day 1 :human 4.9 :critter 2.1}
	{:month 2 :day 2 :human 5.0 :critter 2.5}
	{:month 3 :day 1 :human 4.2 :critter 3.3}
	{:month 3 :day 2 :human 4.0 :critter 3.8})

	(filter #(< (:month %) 3) food-journal)
; ->
	([{:month 1 :day 1 :human 5.3 :critter 2.3}
	{:month 1 :day 2 :human 5.1 :critter 2.0}
	{:month 2 :day 1 :human 4.9 :critter 2.1}
	{:month 2 :day 2 :human 5.0 :critter 2.5})
```

## Some

Some return any value that respect the conditional or `predicate function`.
```
(some #(> (:critter %) 3) food-journal)
; => true

(some #(and (> (:critter %) 3) %) food-journal)
```

## Sort and Sort-by

Ordering the values or the values in a list, vector by a function when used with sort-by

```clojure
(sort [3 1 2])
; => (1 2 3)

(sort-by count ["aaa" "c" "bb"])
; => ("c" "bb" "aaa")
```

## Concat

```clojure
(concat [1 2] [3 4])
; => (1 2 3 4)
```

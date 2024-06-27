# Collection Functions
#clojure #language #programming #functions


The main function of **Collection Abstraction** is `into`, that catch elements from one collection (second) and add to
another one (first):
```clojure
(map identity {:sunlight-reaction "Glitter!"})
; => ([:sunlight-reaction "Glitter!"])

(into {} (map identity {:sunlight-reaction "Glitter!"}))
; => {:sunlight-reaction "Glitter!"}
```
## Conj

It does the same as `into` but with `scalar`. It is common two functions do the same in `Clojure`, however one with `scalar` and
another one with `collections`.
```clojure
(conj [0] 1)
; => [0 1]
```

## Apply

Explode the elements of a sequence and apply the function on it
```clojure
(apply max[0 1 2])
; => 2
```

## Partial

Return a new function with part of it filled with values
```clojure
(def add 10 (partial +10))
(add10 3)
; => 13
```

```Clojure
(defn my-partial
	[partialized-fn & args]
	(fn [& more-args]
	  (apply partialized-fn (into args more-args))))

(def add20 (my-partial + 20))
(add20 3)
; => 23
```
The example above, the value of *add20* is the anonymous function returned by *my-partial*.

## Complement

```clojure
;; Define a predicate function that checks if a number is even
(defn even? [n]
  (zero? (mod n 2)))

;; Use complement to create a predicate that checks if a number is not even (i.e., odd)
(def odd? (complement even?))

;; Test the complement function
; =>(println (even? 4))  ;; Output: true
; =>(println (odd? 4))   ;; Output: false
; =>(println (even? 5))  ;; Output: false
; =>(println (odd? 5))   ;; Output: true
```

### References
- Higginbotham, 2015, p88-93

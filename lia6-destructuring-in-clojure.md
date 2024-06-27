# Destructuring in Clojure
#clojure #language #programming #datastructure

- You can be more concise and readable code. For example:
```clojure
(def my-line [[5 10] [10 20]])
(let [[p1 p2] my-line
      [x1 y1] p1
      [x2 y2] p2]
 (println "Line from (" x1 "," y1 ") to (" x2 ", " y2 ")"))
;= "Line from ( 5 , 10 ) to ( 10 , 20 )"
```
- Large list is a list with 10 elements however, we only get the first three:
```clojure
(def large-list '(1 2 3 4 5 6 7 8 9 10))
(let [[a b c] large-list]
  (println a b c))
;= 1 2 3
```
- What happens with the remaining ones? If we want to capture them:
```clojure
(def large-list '(1 2 3 4 5 6 7 8 9 10))
(let [[a b c & remaining] large-list]
  (println a b c))
  (apply println remaining)
;= 1 2 3
;= (4 5 6 7 8 9 10)
```
- There is [[k89b-associative-destructuring]]# for maps.
- Usually destructuring is passed used for arguments in a function:
```clojure
(defn print-coordinates-1 [point]
  (let [x (first point)
        y (second point)
        z (last point)]
    (println "x:" x ", y:" y ", z:" z)))
; or
(defn print-coordinates-2 [point]
  (let [[x y z] point]
    (println "x:" x ", y:" y ", z:" z)))
```

### References
- https://clojure.org/guides/destructuring

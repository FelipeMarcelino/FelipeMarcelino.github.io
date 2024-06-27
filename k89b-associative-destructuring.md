# Associative Destructuring
#clojure #programming #datastructure #language

- Associative destructuring is for map or other #[[worn-collection-abstraction]] like sets.
- They have the commitment to associate the pair `key-value`.

```clojure
(def client {:name "Super Co."
             :location "Philadelphia"
             :description "The worldwide leader in plastic tableware."})

(let [name (:name client)
      location (:location client)
      description (:description client)]
  (println name location "-" description))
;= Super Co. Philadelphia - The worldwide leader in plastic tableware.
```

### References
- https://clojure.org/guides/destructuring

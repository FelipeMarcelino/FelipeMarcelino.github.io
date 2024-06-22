# First, Rest, and Cons
#clojure #language #programming

It is the main principal operations of all sequences in Clojure language.
The Seq Operations is composed by
- First: Get the current value of a node
- Rest: Get the remaining values of the nodes
- Cons: Adding a node with a new value on the beginning of the sequence

Seq always a return a value that looks and behaves like a list. Seq of map is a list of vectors

The following code return a map function for *JavaScript.*
```javascript
var map = function(list, transform)
	if (list == null){
		return null;
	} else {
		return const (transform (first(list)), map (rest(list), transform));
	}
```

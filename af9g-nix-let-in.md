# Nix: let...in
#nix #nixos #programming #language

Expressions `let...in` are expressions that can access variables inside itself.

Valid ones:
```nix
let
	b = a + 1;
	a = 1;
in
	a + b

let
	attrset = { x = 1; };
in
	attrset.x

let
	a = {
		x = 1;
		y = 2;
		z = 3;
	}
in
	with a; [ x y z ] # or [a.x a.y a.z]

```

Invalid ones
```nix
a = let x = 1; in x;
b = x;
```

[[17dv-inherit]] is a way to assign a variable inside a scope that is nested inside another scope using the same name.

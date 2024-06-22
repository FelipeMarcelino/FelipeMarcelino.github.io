
# Inherit
#nix #nixos #programming #language

It is a way to assign a variable inside a scope that is nested inside another scope using the same name


```nix
let
	x = 1;
	y = 2;
in
	{
		inherit x y; # or { x = 1; y = 2; } => x = x; y = y
	}

let
	a = {x = 1; y = 2;};
in
	{
		inherit (a) x y; # { x = 1; y = 2;} => x = a.x; y = a.y;
	}

let
	inherit ({x = 1; y = 2;}) x y;
in [ x y ] # [ 1 2 ]

```

# Attribute Set
#nix #nixos #language #programming

Collection of value

```nix
attribute-set = {
	a = "hello";
	b = 2;
	c = 2.718;
	d = false;
}; # comments are supported
# Recursive one
rec {
	one = 1;
	two = ones + 1;
	three = two + 1;
}
```
Expressions [[af9g-nix-let-in]] are expressions with the same function of `rec`

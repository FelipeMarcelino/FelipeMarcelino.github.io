# Nix Function
#nix #nixos #language #programming #functional

- The body and the arguments are separated by `:`
- The body is on the right side and the arguments on the left
- Only has one argument
- The calling of the function and its arguments are separated by **space**


## Curried Function

```nix
let
	f = x: y: x + y;
in
	f 1
<LAMBDA>
```


## Attribute Set Arguments (Destructuring)

It is waiting for a specific structure of arguments separated by comma
```nix
let
 f = {a, b}: a + b;
in
 f {a=1; b=2;}
 3

```

## Named Attribute Set Argument

```nix
let
 f = {a,b,...}@args: a + b + arg.c;
in
 f {a=1; b=2; c=3;}
6
```

### References

https://nix.dev/tutorials/nix-language#functions

# String Interpolation
#nix #nixos #programming #language

```nix
let
	name = "nix";
in
	"hello ${name}" # "hello nix"
```
```nix
let
	out = "nix";
in
	"echo ${out} > $out" # $out is a bash variable
```

# Functions Libraries
#nix #nixos #language #programming #functional

- Is composed by `builtins`, `import` and `pkgs.lib`
* `builtins` is composed by base operations such as `toString`
* `import` is used to import files and evaluate it result
* `pks.lib` uses functions extract from [[j8ti-nixos-package]]

One import thing here is that `builtins` and `pkgs.lib` shared common functions with the same implementation.

```bash
$ echo "x:x+1" > file.nix
import ./ file.nix 1 # if you file has a function you can pass the argument directly
```

### References
- https://nix.dev/tutorials/nix-language#function-libraries

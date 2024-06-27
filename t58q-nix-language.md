# Nix Language
#nix #nixos #language #programming #functional

- Nix expression: a piece of code evaluated that produce a `nix value`
- A nix file is a nix expression
- We can evaluate nix expression using `nix repl`
- To exit `nix repl` you can press `:q`
- Break lines, indentation, spaces is only to the code be more readable
- [[9iv3-nix-function]]# only has one argument and are separated by `:`
- [[skjs-functions-libraries]]# are the standard libraries of language, containing `pkgs.lib`, `builtins` and `import`
- The only impurities on the language are the [[hc70-build-inputs]]#, that are composed of file system.
- Nix reference files using the content hash. If It does not know its content, it read the file during the evaluation of
  the derivations
- [eaf9g-nix-let-in]]# are expression on on language that access variable inside itself, or a way to assign variable recursively
- There is something similar to [[af9g-nix-let-in]]# is the [[z8de-attribute-set]]# with rec propriety. The variable can
  be used in the same scope it was defined.
- Nix language can use variables on the code using [[6b5l-string-interpolation]]#. It is possible to escape them to no
  make confuse with bash variables.
- [[17dv-inherit]]# is a way to assign variable on a nested scope.


```nix
nix-repl > 1+2
3
nix-repl > { a.b.c = 1; }
{ a = {...}; }
nix-repl > :p { a.b.c = 1;}
{ a = { b = {c 1;};};}
```

To evaluate one nix file:
```nix
$ echo 1+2 > default.nix
$ nix-instantiate --eval
3
```

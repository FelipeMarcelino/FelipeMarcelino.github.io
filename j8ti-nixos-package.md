# NixOS Package
#nixos #nix #package

A package in NixOS can have multiple programs or none of them. It can be a library for other programs.
```bash
$ nix-shell -p cowsay --run "cowsay nix"
```
The code indicating that the package `cowsay` contains a binary which will run the code with argument `"cowsay nix"`
- The [[38pe-lookup-paths]]# is where path packages are found.

## Pinning Packages
- use a commit
- status: nixos.org
- stable: nixos-21.05 example
- unstable: nixos-unstable

```nix
{pkgs ? import (fetchTarball "https://github.com/nixos/nixpkgs/archive/06278c77bsd162e62df170fec307c83f1812d94b.tar.gz") {} }:
```

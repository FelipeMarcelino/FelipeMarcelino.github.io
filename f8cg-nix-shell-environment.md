# Nix Shell Environment
#system #nix #nixos #env

- It is not commonly reproducible
  - But is possible to create a reproducible one if you pin version of packages
- It is environment with a group of programs you want to use
- `-p` means package or [[j8ti-nixos-package]]
- `--run` is to run one time the program
- Is it possible to created nested environments
- `--pure` remove most of environments variables
- `-I` indicating which source to use
```bash
$ nix-shell -p cowsay --run "cowsay nix" lolcat
# Making them reproducible
$ nix-shell -p --run " git --version" --pure -I
nixpkgs=https://github.com/nixos/nixpkgs/archive/2a601aafdc5605a5133a2ca50a34a3a73377247.tar.gz
# In that case we are indicating which nixpkgs to use using a commit with specific archiving
```

## Declarative Environments
- Runs bash command and set environments variables automatically
- The environments is versioned and reproducible into another machines

Suppose we have a `shell.nix` file with the following code
```nix
let
	nixpkgs = fetchTarball "https://github.com/nixos/nixpkgs/tarball/nixos-23.11";
	pkgs = imports nixpkgs { config = {};; overlays = []; };
in
	pkgs.mkShellNoCC {
		packages = with pkgs; [
			cowsay
			lolcat
		];
		GREETING = "Hello, Nix";
		shellHook = "echo $GREETING | cowsay | lolcat";
	}
```
```bash
$ nix-shell # Find the file shell.nix
[nix-shell] $ cowsay hello | lolcat
```

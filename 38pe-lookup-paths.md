# Lookup Paths
#nix #nixos #language #programming #functional

They are wrapped by `<>` like `<nixpkgs>` which transform into `/nix/var/nix/profiles/per-user/root/channels/nixpkgs`
and are dependents `builtins.nixPath`. Another example `<nixpkgs/lib> =
/nix/var/nix/profiles/per-user/root/channels/nixpkgs/lib`

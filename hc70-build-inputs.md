# Build Inputs
#nix #nixos #language #functional #programming

- Read files from system are the only impurity from Nix language
- Inputs:
  * File System
  * Dedicated Functions
- They need to be explicitly defined
- Derivation use `build inputs` to construct new files
- Nix reference files using the content hash. If It does not know its content, it read the file during the evaluation of
  the derivation

```bash
$ echo 123 > data
"${./data}"
"/nix/store/h1aj5h5nasb2dl564nldr6a8ndy7dh6k-data"
```

## Fetchers

They are used to fetch/collect/grab files from the network, and they are from the [[skjs-functions-libraries]]

- `builtins.fetchUrl`
- `builtins.fetchTarball`
- `builtins.fetchGit`
- `builtins.fetchClosue`

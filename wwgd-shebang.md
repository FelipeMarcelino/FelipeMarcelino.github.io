# Shebang
#bash #language #system #linux

Determines which programs going to use to run the interpreter. For example `#!/bin/sh` runs with `/bin/sh` while
`#!/usr/bin/env python3` execute python 3 using the program env to find the path or the first path with python 3.
`env` invokes the `$PATH`. Example for NixOS `#!/usr/bin/env nix-shell`.

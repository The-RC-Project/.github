# The `__rc` Project
_Simplify maintaining your runtime configurations and setup across devices._

`__rc` uses a modular approach to
spinning up, maintianing and using your `.rc` files. When I was a contractor I frequently had
to setup a new computer porting over my helper functions I created.

## Install
1. Clone this repository into your home directory.
   __note__ This repository will save as a hidden folder named `.__rc`
1. Source `.__rc/.bashrc` inside of your `.bash_profile` or `.bashrc`

```bash
#!/bin/bash
# file: ~/.bashrc/

# We source this projects bashrc file
[[ -f ~/.__rc/.bashrc ]] && source ~/.__rc/.bashrc

```

## Note

By convention the system will use a **login shell** (`.bash_profile`/`.profile`/`.zprofile`) when a user is using a
logged in session. When the user is not using a **login shell** the interactive shell is sourced.  (.bashrc, .zshrc)

It is recommended to source your interactive shell rc from the login rc. This
will keep session consistant between login and interactive sessions.

### Example
- `bash_profile` will source `.bashrc`
- `bashrc`, acting as a wrapper, will source `.__rc/bashrc`

```bash
#!/bin/bash
# file: ~/.bash_profile/

# This source `.bashrc` from `.bash_profile`
[[ -f ~/.bashrc ]] && . ~/.bashrc
```
# Usage

```bash
[[ -f "$HOME/.__rc/bin/sourceShellScripts" ]] && source "$HOME/.__rc/bin/sourceShellScripts"

# Create list of function names to load in shell
list=()

sourceShellScripts "${list[*]}"
```

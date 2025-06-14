### Note
By convention the system will use a **login shell** (`.bash_profile`/`.profile`/`.zprofile`) when a user is using a
logged in session. When the user is not using a **login shell** the interactive shell is sourced.  (.bashrc, .zshrc)

It is recommended to source your interactive shell rc from the login rc. This
will keep session consistant between login and interactive sessions.

#### Example
- `bash_profile` will source `.bashrc`
- `bashrc`, acting as a wrapper, will source `.__rc/bashrc`

```bash
#!/bin/bash
# file: ~/.bash_profile/

# This source `.bashrc` from `.bash_profile`
[[ -f ~/.bashrc ]] && . ~/.bashrc
```

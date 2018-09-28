## Write a file if you forget to sudo before starting vim

This command will save the open file with `sudo` rights

```
:w !sudo tee % >/dev/null
```

You can also map `w!!` to write out a file as root

```
:cnoremap w!! w !sudo tee % >/dev/null
```
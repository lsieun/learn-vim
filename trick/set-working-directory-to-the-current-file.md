# Set working directory to the current file

URL: http://vim.wikia.com/wiki/Set_working_directory_to_the_current_file


## Vim commands

The present working directory can be displayed in Vim with:

```vim
:pwd
```

To change to the directory of the currently open file (this sets the current directory for all windows in Vim):

```vim
:cd %:p:h
```

You can also change the directory only for the current window (each window has a **local current directory** that can be different from Vim's global current directory):

```vim
:lcd %:p:h
```
In these commands, `%` gives the name of the current file, `%:p` gives its full path, and `%:p:h` gives its directory (the "head" of the full path).



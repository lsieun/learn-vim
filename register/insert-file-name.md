# How do I insert the current filename into the contents in Vim?

URL:

- https://unix.stackexchange.com/questions/57555/how-do-i-insert-the-current-filename-into-the-contents-in-vim


The current filename is in the `"%` register, so you can insert it (while in **insert mode**) with `<c-r>%`(按下`Ctrl+R`键，然后输入`%`). In **insert mode**, `<c-r>` specifies that **the next character** is a `register`. 

The full path can be inserted with `<c-r>=expand("%:p")`. You could make a macro of it if you use it often. For more, similar tricks, see `:h expand` and `:h "=`.


Inserts the current filename without the extension at the cursor position, when you are in insert mode.

```vim
:inoremap \fn <C-R>=expand("%:t:r")<CR>
```

To keep the extension use:

```vim
:inoremap \fn <C-R>=expand("%:t")<CR>
```

To insert the absolute path of the directory the file is in use:

```vim
:inoremap \fn <C-R>=expand("%:p:h")<CR>
```

To insert the relative path of the directory the file is in use:

```vim
:inoremap \fn <C-R>=expand("%:h")<CR>
```

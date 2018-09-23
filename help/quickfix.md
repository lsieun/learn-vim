# quickfix

```vim
:help quickfix
```

Vim has a special mode to speedup **the edit-compile-edit cycle**.  **The idea** is to save **the error messages** from **the compiler** in **a file** and use Vim to jump to the errors one by one.  You can examine each problem and fix it, without having to remember all the error messages.

**Each quickfix list** has a unique identifier called **the quickfix ID** and this number will not change within a Vim session. The `getqflist()` function can be used to get the identifier assigned to a list. 

> 这段是讲quickfix list

**A location list** is **a window-local quickfix list**. You get one after commands like `:lvimgrep`, `:lgrep`, `:lhelpgrep`, `:lmake`, etc., which create **a location list** instead of **a quickfix list** as the corresponding `:vimgrep`, `:grep`, `:helpgrep`, `:make` do.

> 这段是讲location list，和quickfix list是有区别的。

**A location list** is associated with **a window** and each window can have a separate location list.  A location list can be associated with only one window.  **The location list** is independent of **the quickfix list**.

> 这段是讲location list和window的关系

## lopen

```vim
:lop[en] [height]	
```

**Open a window** to show **the location** list for **the current window**. Works only when the location list for the current window is present.  You can have more than one location window opened at a time.  Otherwise, it acts the same as "`:copen`".

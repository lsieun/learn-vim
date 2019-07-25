# Vim’s absolute, relative and hybrid line numbers

<!-- TOC -->

- [1. Absolute line numbers](#1-absolute-line-numbers)
- [2. Relative line numbers](#2-relative-line-numbers)
- [3. “Hybrid” line numbers](#3-hybrid-line-numbers)
  - [3.1. Automatic toggling between line number modes](#31-automatic-toggling-between-line-number-modes)
  - [3.2. toggle the line number counting method](#32-toggle-the-line-number-counting-method)
- [4. Reference](#4-reference)

<!-- /TOC -->

Vim doesn’t show line numbers by default, but they can be turned on in your configuration. Besides regular **absolute line numbers**, Vim has **relative** and **“hybrid” modes** to help navigate around files. With some autocommands, it can even toggle between line number modes automatically when you switch files or enter insert mode.

## 1. Absolute line numbers

Using the `number` option, Vim sets up absolute line numbers to show the line number for each line in the file you’re working on.

```vim
:set number
:set nonumber  " turn line numbers off
:set number!   " toggle line numbers
```

Besides being useful for finding a line from a stack trace or a test result, you can use line numbers to help you jump around the file. For example, if you want to go to the tenth line in your file, you’d type `esc` while in insert mode and then `:10` to move to the correct line.

## 2. Relative line numbers

With the `relativenumber` option, each line in your file is numbered relative to the cursor’s current position to show the distance to that line. The current line is marked `0`, the ones above and below it are marked `1`, and so on.

```vim
:set relativenumber
:set norelativenumber  " turn relative line numbers off
:set relativenumber!   " toggle relative line numbers
```

## 3. “Hybrid” line numbers

Since Vim 7.4, enabling `number` and `relativenumber` at the same time produces **hybrid line number mode**. All lines will show their relative number, except for current line, which will show its absolute line number.

```vim
:set number relativenumber
:set nonumber norelativenumber  " turn hybrid line numbers off
:set !number !relativenumber    " toggle hybrid line numbers
```

Hybrid line numbers are what relative line numbers should have been. Instead of having a useless zero on the current line, it uses that space to give you an idea of where you are in the file.

### 3.1. Automatic toggling between line number modes

**Relative line numbers** are helpful when moving around in **normal mode**, but **absolute line numbers** are more suited for **insert mode**. When the buffer doesn’t have focus, it’d also be more useful to show absolute line numbers. For example, when running tests from a separate terminal split, it’d make more sense to be able to see which test is on which absolute line number.

Using some **autocommands**, Vim can switch between line number modes automatically.

```vim
:set number relativenumber

:augroup numbertoggle
:  autocmd!
:  autocmd BufEnter,FocusGained,InsertLeave * set relativenumber
:  autocmd BufLeave,FocusLost,InsertEnter   * set norelativenumber
:augroup END
```

In this example, both absolute and relative line numbers are enabled by default, which produces “hybrid” line numbers. When entering **insert mode**, **relative line numbers** are turned off, leaving **absolute line numbers** turned on. This also happens when the buffer loses focus, so you can glance back at it to see which absolute line you were working on if you need to.

### 3.2. toggle the line number counting method

```vim
" use Ctrl+N to toggle the line number counting method
function! g:ToggleNuMode()
  if &relativenumber == 1
     set number
     set norelativenumber
  else
     set relativenumber
     set nonumber
  endif
endfunction
nnoremap <silent><C-N> :call g:ToggleNuMode()<cr>
```

## 4. Reference

- [Vim’s absolute, relative and hybrid line numbers](https://jeffkreeftmeijer.com/vim-number/)

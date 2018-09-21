# vim-airline

URL: https://github.com/vim-airline/vim-airline


`~/.vim/vimrc`  (Vundle example):

```vim
Plugin 'vim-airline/vim-airline'
Plugin 'vim-airline/vim-airline-themes'
```

```vim
" ==== Airline
set laststatus=2
set t_Co=256
set ttimeoutlen=50
let g:airline#extensions#tabline#enabled = 1
let g:airline#extensions#tabline#left_sep = ' '
let g:airline#extensions#tabline#left_alt_sep = '|'
let g:airline#extensions#tabline#formatter = 'unique_tail'
" let g:airline_section_b = '%{strftime("%Y-%m-%d %T")}'
let g:airline_theme='powerlineish'
```

## vim-airline-themes

URL: https://github.com/vim-airline/vim-airline-themes

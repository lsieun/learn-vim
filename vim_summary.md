

Installation

ex

tab
windows
buffer

windows和buffer的一个形象的理解就是：电视机就是一个Window，而后面的节目就是Buffer。但是又不恰当，因为我们可以通过window往buffer里输入数据，而电视机无法改变节目的内容。

input:
    abbr
    map

script： 自身环境的可塑造性


runtimepath
plugins
    airline -statusline | window

event
    autocmd

window
    colorscheme
    statusline
    line number: number relative number
    jump: H M L z. z<CR> mark
    两个window的应用场景：
        对比两个文件中的内容
        同一个文件，看不同的
        在两个窗口的内容复制

buffer
    file buffer
    copy/delete buffer
    numbered buffer
    ex command: :ls :bN

ex:

    echo @%
    echo expand("%")
    pwd
    set
    colorscheme

code:
    folding
    indent

shell 处部环境（操作系统、程序）的交互
    !ls
    :sh




cmd: normal mode command + ex mode command
window --- status line --- File Tree  --- colorscheme
tab --- window --- buffer
runtimepath --- plugins (windows  / functionality)   --- plugin manager(Vundle)
--------------------------------------------------------------------------------
vim 


Fuzzy File Search: CtrlP
Tag jumping
Autocomplete: YouCompleteMe
File Browsing: NERTTree
Snippets:
Build Integration

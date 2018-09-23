# vim-fugitive

URL:

- https://github.com/tpope/vim-fugitive
- http://vimcasts.org/episodes/fugitive-vim---a-complement-to-command-line-git/


The `fugitive` plugin, by Tim Pope, is **a git wrapper** for `Vim`. It complements the command line interface to `git`, but doesn’t aim to replace it.

Using the `:Git` command, you can run any arbitrary `git` command from inside Vim. I prefer to switch to the `shell` for anything that generates a log of output, such as `git log` for example. But commands that generate little or no output are fair game for running from inside `Vim` (`:Git checkout -b experimental` for example).

> 这段的三个意思：  
> （1）在Vim中使用`:Git`相当于在Shell中使用`git`。
> （2）作者说，如果有很长的output，他会选择在shell中执行git命令。  
> （3）对于output很少的命令，在Vim中执行。

At Vim’s command line, **the `%` symbol has a special meaning**: it expands to **the full path of the current file**. You can use this to run any `git` command that expects a filepath as an argument, making the command act on the current file. But `fugitive` also provides a few convenience methods, some of which are summarized in this table:



| git             | fugitive | action                                                   |
| --------------- | -------- | -------------------------------------------------------- |
| `:Git add %`      | `:Gwrite`  | Stage the current file to the index.                     |
| `:Git checkout %` | `:Gread`   | Revert current file to last checked in version.          |
| `:Git rm %`     | `:Gremove` | Delete the current file and the corresponding Vim buffer. |
| `:Git mv %`       | `:Gmove`   | Rename the current file and the corresponding Vim buffer. |

> 上面介绍git的四个常用命令

The `:Gcommit` command opens up a commit window in a split window. One advantage to using this, rather than running `git` commit in the shell, is that you can use **Vim’s keyword autocompletion** when composing your commit message.

> 这段介绍git commit命令

The `:Gblame` command opens a vertically split window containing annotations for each line of the file: the last commit reference, with author and timestamp. The split windows are bound, so that when you scroll one, the other window will follow.

> 这段介绍git blame命令

## Further Reading

- `:help cmdline-special`
- `:help :_%`
- `ctlr-n/ctrl-p` keyword autocompletion
- `:help 'complete'`
- `:help :Git`
- `:help :Gwrite`
- `:help :Gread`
- `:help :Gremove`
- `:help :Gmove`
- `:help :Gcommit`
- `:help :Gblame`



# edit

`:edit`: Edit the current file. This is useful to re-edit the current file, when it has been changed outside of Vim.

这段理解：这个`:edit <filename>`有两个作用

- （1） 打一个新文件，就是将这个新文件加入到Vim的buffer中去
- （2） 重新加载这个文件。

`：edit!`: Edit the current file always. Discard any changes to the current buffer. This is useful if you want to start all over again.

这个`:edit!`的作用就是丢弃已经编辑的内容，从新开始。
